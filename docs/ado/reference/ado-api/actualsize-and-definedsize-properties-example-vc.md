---
title: Примеры свойств ActualSize и DefinedSize (Visual c++) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActualSize property [ADO], VC++ example
- DefinedSize property [ADO], VC++ example
ms.assetid: 05f7cc97-b806-41d2-939d-a955d10844c4
author: rothja
ms.author: jroth
ms.openlocfilehash: 092c67ec3fef6705d103e87cd5e47adc37397475
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760700"
---
# <a name="actualsize-and-definedsize-properties-example-vc"></a>Пример свойств ActualSize и DefinedSize (Visual c++)
В этом примере используются свойства [ActualSize](../../../ado/reference/ado-api/actualsize-property-ado.md) и [DefinedSize](../../../ado/reference/ado-api/definedsize-property.md) для вывода определенного размера и фактического размера поля.  
  
## <a name="example"></a>Пример  
  
```  
// BeginActualSizeCpp.cpp  
// compile with: /EHsc  
#import "msado15.dll" no_namespace rename("EOF", "EndOfFile")  
  
#include <ole2.h>  
#include <stdio.h>  
#include "conio.h"   
  
// Function declarations  
inline void TESTHR(HRESULT x) { if FAILED(x) _com_issue_error(x); };  
void ActualSizeX();  
void PrintProviderError(_ConnectionPtr pConnection);  
  
int main() {  
   if (FAILED(::CoInitialize(NULL)))  
      return -1;  
   ActualSizeX();  
   ::CoUninitialize();  
}  
  
void ActualSizeX() {  
   HRESULT hr = S_OK;  
  
   // Define ADO object pointers. Initialize pointers on define.  
   // These are in the ADODB::  namespace.  
   _RecordsetPtr pRstStores = NULL;  
  
   // Define Other variables  
   _bstr_t strMessage;  
   _bstr_t strCnn("Provider='sqloledb'; Data Source='My_Data_Source'; Initial Catalog='pubs'; Integrated Security='SSPI';");  
  
   try {  
      // Open a recordset for the stores table.  
      TESTHR(pRstStores.CreateInstance(__uuidof(Recordset)));  
  
      // You have to explicitly pass the Cursor type and LockType to the Recordset here.  
      hr = pRstStores->Open("stores", strCnn, adOpenForwardOnly, adLockReadOnly, adCmdTable);  
  
      // Loop through the recordset displaying the contents of the stor_name field,   
      // the field's defined size, and its actual size.  
      pRstStores->MoveFirst();  
  
      while (!(pRstStores->EndOfFile)) {  
         strMessage = "Store Name: ";  
         strMessage += (_bstr_t)pRstStores->Fields->Item["stor_name"]->Value + "\n";  
         strMessage += "Defined Size: ";   
         strMessage += (_bstr_t)pRstStores->Fields->Item["stor_name"]->DefinedSize + "\n";  
         strMessage += "Actual Size: ";  
         strMessage += (_bstr_t) pRstStores->Fields->Item["stor_name"]->ActualSize + "\n";   
  
         printf("%s\n",(LPCSTR)strMessage);  
         pRstStores->MoveNext();  
      }  
   }  
   catch(_com_error &e) {  
      _variant_t vtConnect = pRstStores->GetActiveConnection();  
  
      // GetActiveConnection returns connect string if connection  
      // is not open, else returns Connection object.  
      switch(vtConnect.vt) {  
         case VT_BSTR:  
            printf("Error:\n");  
            printf("Code = %08lx\n", e.Error());  
            printf("Message = %s\n", e.ErrorMessage());  
            printf("Source = %s\n", (LPCSTR) e.Source());  
            printf("Description = %s\n", (LPCSTR) e.Description());  
            break;  
         case VT_DISPATCH:  
            PrintProviderError(vtConnect);  
            break;  
         default:  
            printf("Errors occured.");  
            break;  
      }  
   }  
  
   // Clean up objects before exit.  
   if (pRstStores)  
      if (pRstStores->State == adStateOpen)  
         pRstStores->Close();  
}  
  
void PrintProviderError(_ConnectionPtr pConnection) {  
   // Print Provider Errors from Connection object.  
   // pErr is a record object in the Connection's Error collection.  
   ErrorPtr pErr = NULL;  
   long nCount = 0;      
   long i = 0;  
  
   if ( (pConnection->Errors->Count) > 0) {  
      nCount = pConnection->Errors->Count;  
      // Collection ranges from 0 to nCount -1.  
      for (i = 0 ; i < nCount ; i++) {  
         pErr = pConnection->Errors->GetItem(i);  
         printf("\t Error number: %x\t%s", pErr->Number,(LPCSTR ) pErr->Description);  
      }  
   }  
}  
```  
  
 **Имя хранилища: водосчитывание книги**  
**Определенный размер: 40**  
**Фактический размер: 19**  
**Имя хранилища: Барнум**  
**Определенный размер: 40**  
**Фактический размер: 8**  
**Имя хранилища: News & Бревс**  
**Определенный размер: 40**  
**Фактический размер: 12**  
**Имя хранилища: doc-U-белье: Quality и книги**  
**Определенный размер: 40**  
**Фактический размер: 36**  
**Имя хранилища: Фрикативе Букшоп**  
**Определенный размер: 40**  
**Фактический размер: 18**  
**Имя хранилища: Букбеат**  
**Определенный размер: 40**  
**Фактический размер: 8**   
## <a name="see-also"></a>См. также  
 [Свойство ActualSize (ADO)](../../../ado/reference/ado-api/actualsize-property-ado.md)   
 [Свойство DefinedSize](../../../ado/reference/ado-api/definedsize-property.md)
