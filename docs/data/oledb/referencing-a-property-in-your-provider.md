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
ms.openlocfilehash: b250e29acc964e1fb1273d02a3b1ea93c087e5c4
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082745"
---
# <a name="referencing-a-property-in-your-provider"></a>Обращение к свойству в поставщике

Для свойства, которое требуется найти группы свойств и идентификатор свойства. Дополнительные сведения см. в разделе [свойства OLE DB](/previous-versions/windows/desktop/ms722734) в *Справочник программиста OLE DB по*.  
  
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