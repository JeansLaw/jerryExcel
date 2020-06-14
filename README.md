#Demo

##新建Excel文件
    import os
    import jerryExcel
    
    # step 1
    excel=jerryExcel.ExcelUtil()
    path=os.getcwd()
    # 设置文件保存路径
    filepath=os.path.join(path,"test.xls")
    # 传入文件路径 以及表名
    newExcel=excel.NewExcelFile(filepath,"sheet1")
    
    # step 2 准备写入的数据
    content=["test1","test2","test3"]
    newExcel.write(content)
    # 传空值相当于换行
    newExcel.write()
    newExcel.write(content)
    # step 3 保存
    newExcel.save()

## 追加excel数据

    # 追加excel文件
    
    # step 1 设置文件路径
    excel=jerryExcel.ExcelUtil()
    path=os.getcwd()
    filepath=os.path.join(path,"test.xls")
    addtion=excel.AddtionWrite(filepath)
    # step 2 写入数据
    content=["test1","test2","test3"]
    addtion.write(content)
    addtion.write()
    addtion.write(content)
    # step 3 保存
    addtion.save()
 
 ## 读取excel数据   
    # step 1 设置文件路径
    excel = jerryExcel.ExcelUtil()
    path = os.getcwd()
    filepath = os.path.join(path, "test.xls")
    cursor = excel.Cursor(filepath)
    # step 2 读取数据
    datas = cursor.read(ignoreFirstLine=False, index=0)
    # step 3 遍历输出数据
    for data in datas:
        print(data)