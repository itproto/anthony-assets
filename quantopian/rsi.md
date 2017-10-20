# RSI
    #Import talib library
    import talib
    
    # Load historical data for the stocks
    prices = data.history(context.stocks, 'price', 20, '1d')
    
    # Loop through our list of stocks
    for stock in context.stocks:
      rsi = talib.RSI(prices[stock], timeperiod=14)[-1]
