---
title: Обращение к свойству в поставщике
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
ms.openlocfilehash: ecb11c54d4c5926fbead0196c441ec23e8b0891f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509519"
---
# <a name="referencing-a-property-in-your-provider"></a>Обращение к свойству в поставщике

Найдите группу свойств и идентификатор свойства для нужного свойства. Дополнительные сведения см. в разделе [OLE DB свойства](/previous-versions/windows/desktop/ms722734(v=vs.85)) в **справочнике по программированию OLE DB**.

В следующем примере предполагается, что вы пытаетесь получить свойство из набора строк. Код для использования сеанса или команды аналогичен, но использует другой интерфейс.

Создайте объект [кдбпропсет](../../data/oledb/cdbpropset-class.md) , используя группу свойств в качестве параметра конструктора. Пример:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
```

Вызовите [AddProperty](./cdbpropset-class.md#addproperty), ПЕРЕДАВ ему идентификатор свойства и значение, присваиваемое свойству. Тип значения зависит от свойства, которое вы используете.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);

propset.AddProperty(DBPROP_IRowsetChange, true);

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);
```

Используйте `IRowset` интерфейс для вызова `GetProperties` . Передайте набор свойств в качестве параметра. Вот окончательный код:

```cpp
CAgentRowset<CCustomCommand>* pRowset = (CAgentRowset<CCustomCommand>*) pThis;

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

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
