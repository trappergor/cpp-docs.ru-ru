---
title: Передача проверка на совместимость с OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 70607e0518d13015ee11895270ad3306cd3da24b
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808177"
---
# <a name="passing-ole-db-conformance-tests"></a>Проверка на совместимость с OLE DB

Чтобы сделать более согласованным поставщиков, Data Access SDK предоставляет набор тестов на совместимость с OLE DB. Тесты проверяют все аспекты вашего поставщика и дают возможность степени быть уверены, функционирует как ожидалось. Проверка на совместимость OLE DB можно найти на Microsoft Data Access SDK. В этом разделе описываются действия, которые следует выполнить для проверки на совместимость. Сведения о выполнении тестов на совместимость OLE DB см. в SDK.  
  
## <a name="running-the-conformance-tests"></a>Выполнение тестов на совместимость  

В Visual C++ 6.0 шаблоны поставщика OLE DB добавлен ряд функций привязки, которые позволяют проверять значения и свойства. Большая часть этих функций были добавлены в ответ тестов на совместимость.  
  
> [!NOTE]
> Необходимо добавить несколько функций проверки для поставщика для проверки на совместимость OLE DB.  
  
Для этого поставщика требуется две процедуры проверки. Первая программа, `CRowsetImpl::ValidateCommandID`, является частью класса набора строк. Она вызывается во время создания набора строк с помощью шаблонов поставщика. В образце используется эта подпрограмма для информирования потребителей, что индексы не поддерживаются. Первый вызов направляется `CRowsetImpl::ValidateCommandID` (Обратите внимание, что поставщик использует `_RowsetBaseClass` typedef, добавлены в схему интерфейсов для `CMyProviderRowset` в [Поддержка закладок поставщиками](../../data/oledb/provider-support-for-bookmarks.md), поэтому нет необходимости необходимость ввода длинной строки шаблона аргументы). Далее, если параметр индекса не равно NULL, возвращается значение DB_E_NOINDEX (это указывает, необходимо использовать индекс). Дополнительные сведения о идентификаторы команд см. в спецификации OLE DB и найдите `IOpenRowset::OpenRowset`.  
  
В следующем коде приведен `ValidateCommandID` процедуры проверки:  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
Шаблоны поставщика вызывают `OnPropertyChanged` метод всякий раз, когда кто-то изменяет свойство на `DBPROPSET_ROWSET` группы. Если вы хотите обрабатывать свойства для других групп, можно добавить их в соответствующий объект (то есть `DBPROPSET_SESSION` проверок перейдите `CMyProviderSession` класса).  
  
Код сначала проверяет, связано ли свойство в другой. Если свойство является, он присваивает `DBPROP_BOOKMARKS` свойства `True`. Приложение В спецификации OLE DB содержит сведения о свойствах. Эти сведения также сообщает ли свойство привязанной к другой.  
  
Вы также можете добавить `IsValidValue` в код. Шаблоны вызывают `IsValidValue` при попытке задать свойство. Нужно переопределить этот метод, если требуется дополнительная обработка при задании значения свойства. Вы может иметь одно из этих методов для каждого набора свойств.  
  
## <a name="see-also"></a>См. также  

[Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)