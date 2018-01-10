---
title: "Обращение к свойству в поставщике | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e39d012f126d44477bcb27f43b0a1119583a7ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="referencing-a-property-in-your-provider"></a>Обращение к свойству в поставщике
Для свойства, которое требуется найти группы свойств и идентификатор свойства. Дополнительные сведения см. в разделе [свойства OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) в *Справочник программиста OLE DB*.  
  
 В следующем примере предполагается, что вы пытаетесь получить свойство из набора строк. Код для использования сеанса или команды аналогичен, но использует другой интерфейс.  
  
 Создание [CDBPropSet](../../data/oledb/cdbpropset-class.md) объекта, используя группу свойств в качестве параметра конструктору. Пример:  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Вызовите [AddProperty](../../data/oledb/cdbpropset-addproperty.md), передав идентификатор свойства и значение, присваиваемое свойству. Тип значения, зависит от свойства, которое вы используете.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Используйте `IRowset` интерфейс для вызова **GetProperties**. Передайте свойство в качестве параметра. Ниже приведен конечный код:  
  
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
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)