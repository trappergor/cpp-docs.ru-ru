---
title: "Переопределение динамического метода доступа | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "методы доступа [C++], dynamic"
  - "динамические методы доступа"
  - "переопределение, динамические методы доступа"
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Переопределение динамического метода доступа
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При использовании динамического метода доступа, например `CDynamicAccessor`, метод команды **Open** автоматически создает метод доступа на основе сведений о столбцах открытого набора строк.  Существует возможность переопределения динамического метода доступа для управления способом связывания столбцов.  
  
 Чтобы переопределить динамический метод доступа, следует передать методу `CCommand::Open` в качестве последнего параметра значение **false**.  Тем самым предотвращается автоматическое создание метода доступа методом **Open**.  После этого можно вызывать методы `GetColumnInfo` и `AddBindEntry` для каждого столбца, который необходимо связать.  В следующем примере кода показано, как это сделать:  
  
```  
USES_CONVERSION;  
double   dblProductID;  
  
CCommand<CDynamicAccessor> product;  
// Open the table, passing false to prevent automatic binding   
product.Open(session, _T("Select * FROM Products"), NULL, NULL, DBGUID_DEFAULT, false);  
  
ULONG         nColumns;  
DBCOLUMNINFO*   pColumnInfo;  
// Get the column information from the opened rowset.  
product.GetColumnInfo(&nColumns, &pColumnInfo);  
  
// Bind the product ID as a double.  
pColumnInfo[0].wType          = DBTYPE_R8;  
pColumnInfo[0].ulColumnSize = 8;  
product.AddBindEntry(pColumnInfo[0]);  
  
// Bind the product name as it is.  
product.AddBindEntry(pColumnInfo[1]);  
  
// Bind the reorder level as a string.  
pColumnInfo[8].wType          = DBTYPE_STR;  
pColumnInfo[8].ulColumnSize = 10;  
product.AddBindEntry(pColumnInfo[8]);  
  
// You have finished specifying the bindings. Go ahead and bind.  
product.Bind();  
// Free the memory for the column information that was retrieved in   
// previous call to GetColumnInfo.  
CoTaskMemFree(pColumnInfo);  
  
char*   pszProductName;  
char*   pszReorderLevel;  
bool   bRC;  
  
// Loop through the records tracing out the information.  
while (product.MoveNext() == S_OK)  
{  
   bRC = product.GetValue(1, &dblProductID);  
   pszProductName   = (char*)product.GetValue(2);  
   pszReorderLevel  = (char*)product.GetValue(9);  
  
   ATLTRACE(_T("Override = %lf \"%s\" \"%s\"\n"), dblProductID,  
      A2T(pszProductName), A2T(pszReorderLevel));  
}  
```  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)