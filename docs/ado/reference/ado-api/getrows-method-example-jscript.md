---
title: Пример метода GetRows (JScript) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- JScript
helpviewer_keywords:
- Getrows method [ADO], JScript example
ms.assetid: d33467a5-5a56-450d-98c1-c3ce6f9f103c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ba091ff7db668cc049c50eeb26492a2c9ee3422
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760030"
---
# <a name="getrows-method-example-jscript"></a>Пример метода GetRows (JScript)
В этом примере метод [GetRows](../../../ado/reference/ado-api/getrows-method-ado.md) используется для получения всех строк таблицы *Кустиомерс* из [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md) и для заполнения массива результирующими данными. Метод **GetRows** возвращает меньше требуемого числа строк в двух случаях: или, если был достигнут [конец файла](../../../ado/reference/ado-api/bof-eof-properties-ado.md) , или если **GetRows** попытался получить запись, удаленную другим пользователем. Функция возвращает **значение false** только в том случае, если происходит второй вариант. Вырежьте и вставьте следующий код в Блокнот или другой текстовый редактор и сохраните его как **жетровсжс. ASP**.  
  
```  
<!-- BeginGetRowsJS -->  
<%@ LANGUAGE="JScript" %>  
<%// use this meta tag instead of adojavas.inc%>  
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" -->  
  
<html>  
  
<head>  
<title>ADO Recordset.GetRows Example (JScript)</title>  
<style>  
<!--  
BODY {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
.thead {  
   background-color: #008080;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.thead2 {  
   background-color: #800000;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.tbody {   
   text-align: center;  
   background-color: #f7efde;  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
    }  
-->  
</style>  
</head>  
  
<body bgcolor="white">  
  
<h1>ADO Recordset.GetRows Example (JScript)</h1>  
    <!-- Page text goes here -->  
<%  
        var Connect = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" +  
            "Initial Catalog='Northwind';Integrated Security='SSPI';";  
    var mySQL = "select * from customers;";  
    var showblank = " ";  
    var shownull = "-null-";  
  
    var connTemp = Server.CreateObject("ADODB.Connection");  
  
    try  
    {  
        connTemp.Open(Connect);  
        var rsTemp = Server.CreateObject("ADODB.Recordset");  
        rsTemp.ActiveConnection = connTemp;  
        rsTemp.CursorLocation = adUseClient;  
        rsTemp.CursorType = adOpenKeyset;  
        rsTemp.LockType = adLockOptimistic;  
        rsTemp.Open(mySQL);  
  
        rsTemp.MoveFirst();  
  
        if (rsTemp.RecordCount == 0)  
        {  
            Response.Write("No records matched ");  
            Response.Write (mySQL & "So cannot make table...");  
            connTemp.Close();  
            Response.End();  
        } else  
        {  
            Response.Write('<table width="100%" border="2">');  
            Response.Write('<tr class="thead2">');  
  
            //  Headings On The Table for each Field Name  
            for (var i=0; i<rsTemp.Fields.Count; i++)  
            {  
                fieldObject = rsTemp.fields(i);  
                Response.Write('<td width="' + Math.floor(100 / rsTemp.Fields.Count) + '%">' + fieldObject.name + "</td>");  
            }  
  
            Response.Write("</tr>");  
  
            // JScript doesn't support multi-dimensional arrays  
            // so we'll convert the returned array to a single  
            // dimensional JScript array and then display the data.  
            tempArray = rsTemp.GetRows();  
            recArray = tempArray.toArray();  
  
            var col = 1;  
            var maxCols = rsTemp.Fields.Count;  
  
            for (var thisField=0; thisField<recArray.length; thisField++)  
            {  
                if (col == 1)  
                    Response.Write('<tr class="tbody">');  
                if (recArray[thisField] == null)  
                        recArray[thisField] = shownull;  
                if (recArray[thisField] == "")  
                        recArray[thisField] = showblank;  
                Response.Write("<td>" + recArray[thisField] + "</td>");  
                col++  
                if (col > maxCols)  
                {  
                    Response.Write("</tr>");  
                    col = 1;  
                }  
            }  
            Response.Write("</table>");  
        }  
    }  
    catch (e)  
    {  
        Response.Write(e.message);  
    }  
    finally  
    {  
        // clean up  
        if (rsTemp.State == adStateOpen)  
            rsTemp.Close;  
        if (connTemp.State == adStateOpen)  
            connTemp.Close;  
        rsTemp = null;  
        connTemp = null;  
    }  
%>  
  
</body>  
  
</html>  
<!-- EndGetRowsJS -->  
```  
  
## <a name="see-also"></a>См. также  
 [Метод GetRows (ADO)](../../../ado/reference/ado-api/getrows-method-ado.md)   
 [Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
