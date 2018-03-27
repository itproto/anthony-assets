const express = require('express');
const app = express();
const router = express.Router();
const homeRoute = router.route('/');
const cors = require('cors');
const moment = require('moment-timezone');

const axios = require('axios');
const endPoint = "https://api.iextrading.com/1.0";
const ticker = 'aapl';
const url = endPoint + '/stock/' + ticker + '/quote';


app.use('/', express.static(__dirname + "/"));
app.use(cors());

//homeRoute.get((req, res,next)=>{
    
    axios.get(url)
    .then(function (res) {  
        
        let data = res.data;
        let symbol = data.symbol;
        let company = data.companyName;
        let exchange = data.primaryExchange;
        let sector = data.sector;
        let open = data.open;
        let openTime = moment.tz(data.openTime, 'America/New_York').format('hh:mm:ss A');
        let high = data.high;
        let low = data.low;
        let close = data.close;
        let closeTime = moment.tz(data.closeTime, 'America/New_York').format('hh:mm:ss A');
        let source = data.latestSource;
        let latestPrice = data.latestPrice;
        let latestTime = moment.tz(data.latestTime, 'America/New_York').format('hh:mm:ss A');
        let volume = data.latestVolume;
        

        let query = {            
            "symbol": symbol,
            "company": company,
            "exchange": exchange,
            "section": sector,
            "open": open,
            "high": high,
            "low": low,
            "close": close,
            "closeTime": closeTime,
            "latestPrice": latestPrice,
            "latestTime": latestTime,
            "source": source,
            "volume": volume,
            "openTime": openTime
        }

        console.log(query)
        
        
    })
    .catch(function (error) {
        console.log(error);
        
    });

    
//});

app.use('/', router);

app.listen(8080);

console.log('http://localhost:8080');
