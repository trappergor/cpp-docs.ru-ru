---
title: Обращение к свойству в поставщике | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec2a52949754e6b19730d5ef025f958d517f6fd0
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341040"
---
# <a name="referencing-a-property-in-your-provider"></a>Обращение к свойству в поставщике
Для свойства, которое требуется найти группы свойств и идентификатор свойства. Дополнительные сведения см. в разделе [свойства OLE DB](https://msdn.microsoft.com/library/ms722734.aspx) в *Справочник программиста OLE DB по*.  
  
 В следующем примере предполагается, что вы пытаетесь получить свойство из набора строк. Код для использования команды или сеанса, похоже, но используется другой интерфейс.  
  
 Создание [CDBPropSet](../../data/oledb/cdbpropset-class.md) объекта, используя группу свойств в качестве параметра в конструктор. Пример:  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Вызовите [AddProperty](../../data/oledb/cdbpropset-addproperty.md), передавая ему идентификатор свойства и значение, присваиваемое свойству. Тип значения, зависит от свойства, которое вы используете.  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IRowsetChange, true);  

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Используйте `IRowset` интерфейс, необходимо вызвать `GetProperties`. Передайте свойство в качестве параметра. Ниже приведен конечный код:  
  
```cpp  
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