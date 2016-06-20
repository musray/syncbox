## win32com的基本Excel操作
### 新建Excel应用
	
	import win32com.client as win32
	excel = win32.gencache.EnsureDispatch('Excel.Application')
	visibility: excel.Visible = True (or False)
	
	
### 打开Excel文件
	wb = excel.Workbooks.Open('xlsxFileNameString')

### 操作sheet页
	sh = wb.Worksheets(sheetIndex) # int
	sh = wb.Worksheets('sheetName') # string
	wb.Sheets
	wb.Sheets.Count
	for sh in wb.Sheets
		sh.Name
	
### 操作行
		sh.Rows(1:1)
		values = sh.Rows(2:2).Value # return a tuple of the tuple of all values in the 2nd row
		# use values[0] to access inner tuple which hosts all the values ( len(values[0] ==16384 )
	
### 操作单元格
		sh.Range('A1')
		b2 = sh.Range('B2').Value
		sh.Range('C3').Value = 'egg'
	
### 按区域操作表格
		values1 = sh.Rows('2:5').Value
		len(values1) == 4  # True
		len(values1[0]) == 16384
		len(values1[0]) == 16384
		values2 = sh.Range('A1:C10').Values
		len(values2) == 10
		len(values2[0]) == 3  # values2[0] represents the first row in the selected range

	
		
		
		

