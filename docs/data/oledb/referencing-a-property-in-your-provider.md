---
title: "Обращение к свойству в поставщике | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "поставщики OLE DB, свойства"
  - "ссылки, на свойства (поставщики)"
  - "ссылки на свойства (поставщики)"
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обращение к свойству в поставщике
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определите группу и идентификатор требуемого свойства.  Дополнительные сведения см. в разделе [Свойства OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) *Справочника программиста по OLE DB*.  
  
 В следующем примере предполагается, что пользователь пытается получить свойство из набора строк.  Код для использования сеанса или команды аналогичен, но в нем используется другой интерфейс.  
  
 Следует создать объект [CDBPropSet](../Topic/CDBPropSet%20Class.md), используя группу свойств в качестве параметра конструктора.  Примеры.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Вызовите метод [AddProperty](../../data/oledb/cdbpropset-addproperty.md), передав идентификатор свойства и значение, которое ему надо присвоить.  Тип значения этого свойства зависит от используемого свойства.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Используйте интерфейс `IRowset` для вызова метода **GetProperties**.  Передайте свойство в качестве параметра.  Ниже приведен конечный код:  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  
DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  
HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)