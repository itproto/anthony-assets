# Price History

    price_history = data.history(context.stocks, fields="price", bar_count=2, frequency="1d")
    
    for stock in context.stocks:
        
        prev_bar = price_history[stock][-2]
        curr_bar = price_history[stock][-1]
        
        print(prev_bar,curr_bar)
    pass
