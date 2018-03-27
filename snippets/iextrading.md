var moment = require('moment-timezone');


var baseTime = new Date(Date.UTC(1970,0,1,0,0,0,0)); //Date.UTC(year, month[, day[, hour[, minute[, second[, millisecond]]]]])
var IEXDate = new Date(Date.UTC(1970,0,1,0,0,0,1521811800352))

//var IEXDate = baseTime

var IEXUTCDate = IEXDate.getDate()
var IEXMonth= IEXDate.getMonth() + 1
var IEXDay = IEXDate.getUTCDay()
var IEXYear = IEXDate.getFullYear()
var IEXHour = IEXDate.getUTCHours()
var IEXMilSec = IEXDate.getUTCMilliseconds()
var IEXMin = IEXDate.getUTCMinutes()
var IEXSec = IEXDate.getUTCSeconds()


//console.log(new Date(IEXMonth + "/" + IEXUTCDate + "/" + IEXYear + IEXHour))
var finalDate = new Date(IEXDate);
console.log(finalDate.getTimezoneOffset());
console.log(finalDate);
var timeStamp = 1521811800352;

console.log(moment.tz(timeStamp,"America/New_York").format('MMMM DD, YYYY hh:mm:ss'))
