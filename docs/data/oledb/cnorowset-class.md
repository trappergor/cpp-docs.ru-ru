---
title: Класс CNoRowset | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e92c9bfb49bbb64faca633f04bb87f40028b6e1e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339566"
---
# <a name="cnorowset-class"></a>Класс CNoRowset
Можно использовать в качестве аргумента шаблона (`TRowset`) для [CCommand](../../data/oledb/ccommand-class.md) или [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
### <a name="parameters"></a>Параметры  
 *TAccessor*  
 Класс, метод доступа. Значение по умолчанию — `CAccessorBase`.  
  
## <a name="remarks"></a>Примечания  
 Используйте `CNoRowset` как аргумент шаблона, если команда не возвращает набор строк.  
  
 `CNoRowset` реализует следующие методы-заглушки, каждый из которых соответствуют другим методам класса метода доступа:  
  
-   `BindFinished` — Указывает, когда привязка завершена (возвращает `S_OK`).  
  
-   `Close` -Освобождает строки и текущий интерфейс IRowset.  
  
-   `GetIID` — Извлекает идентификатор интерфейса точки подключения.  
  
-   `GetInterface` — Извлекает интерфейс.  
  
-   `GetInterfacePtr` — Извлекает инкапсулированный указатель на интерфейс.  
  
-   `SetAccessor` — Задает указатель метода доступа.  
  
-   `SetupOptionalRowsetInterfaces` — Устанавливает дополнительные интерфейсы для набора строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)