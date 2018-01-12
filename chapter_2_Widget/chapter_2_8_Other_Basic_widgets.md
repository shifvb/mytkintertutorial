### 一些用于特定输入的控件

------------------------------


1. `tk.Spinbox`

    此控件可以用来限制用户输入整数。默认的按钮太小了，所以设置了一下字体大小。
    
    可以使用`from_`属性和`to`属性限制输入范围(非强制，用户直接输入可以越界)：
    
        sb = tk.Spinbox(root, from_=1, to=30, font=font.Font(size=100))
        sb.pack()
        # 用来显示Spinbox当前值的label
        label = tk.Label(root, text="current value: ")
        label.pack()
        # 点击按钮显示Spinbox当前值
        def btn_callback():
            label.config(text="current value: {}".format(sb.get()))
        tk.Button(root, text="show spinbox value",command=btn_callback).pack()

    ![](static/4be2ff19298e36005d275e9382b5b86a.png)
    
    也可以使用`values`属性指定输入范围(非强制，用户直接输入可以越界)：
    
        sb = tk.Spinbox(root, values=[-1, 2, 3, 10], font=font.Font(size=100))
        sb.pack()
        # 用来显示Spinbox当前值的label
        label = tk.Label(root, text="current value: ")
        label.pack()
        # 点击按钮显示Spinbox当前值
        def btn_callback():
            label.config(text="current value: {}".format(sb.get()))
        tk.Button(root, text="show spinbox value", command=btn_callback).pack()
    
    ![](static/e54a14c9581c8ef1a5c54a10b4826569.png)
    
2. `tk.Scale`

    使用拖动方式确定用户输入，可以使用`from_`属性和`to`属性指定值域，而`orient`属性指定方向
    
        s = tk.Scale(root, from_=-4, to=4, orient=tk.HORIZONTAL)
        s.pack()
        # 显示当前Scale的值
        label = tk.Label(root, text="current value")
        label.pack()
        def btn_callback():
            label.configure(text="current value: {}".format(s.get()))
        tk.Button(root, text="show current value", command=btn_callback).pack()

    ![](static/15af3b304ba161623074dae16f2fc836.png)

3. `tk.OptionMenu`

    显示一个看起来很过时的下拉菜单
    
        v = tk.StringVar(value="apple")
        om = tk.OptionMenu(root, v, "doge", "neko")
        om.pack()
        # 显示当前OptionMenu的值
        label = tk.Label(root, text="current value")
        label.pack()
        def btn_callback():
            label.configure(text="current value: {}".format(v.get()))
        tk.Button(root, text="show current value", command=btn_callback).pack()
        
    ![](static/f4301eb598284f5d84ee2eac1fae247e.png)    