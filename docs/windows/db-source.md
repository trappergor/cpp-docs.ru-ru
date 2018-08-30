---
title: db_source | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bad61c157926fd417467afaa2d97d0db517430f6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201560"
---
# <a name="dbsource"></a>db_source

Создает подключение к источнику данных.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_source(
   db_source,
   name,
   hresult
) ]
```

### <a name="parameters"></a>Параметры

*db_source*  
Строка подключения, используемая для подключения к источнику данных. Формат строки подключения, см. в разделе [строки соединения и ссылки на данные](/previous-versions/windows/desktop/ms718376\(v=vs.85\)) в Майкрософт данных Access Components (MDAC) SDK.

*name* (необязательно)  
При использовании **db_source** в классе, *имя* — это экземпляр объекта источника данных, имеющий **db_source** атрибут, примененный к нему (см. Пример 1). При использовании **db_source** , встроенный в реализации метода, *имя* — переменная (локальный метода), которая может использоваться для доступа к данным источника (см. Пример 2). Передать его *имя* для *source_name* параметр `db_command` должен быть сопоставлен команды в источнике данных.

*HRESULT* (необязательно)  
Определяет переменную, которая будет получать значение HRESULT, равное этой команды базы данных. Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Примечания

**db_source** создает [CDataSource](../data/oledb/cdatasource-class.md) и [CSession](../data/oledb/csession-class.md) объект, который представляет соединение с источником данных потребитель OLE DB.

При использовании **db_source** в классе, `CSession` объект становится членом класса.

При использовании **db_source** в методе, этот код выполняется в области действия метода и `CSession` объект создается как локальная переменная.

**db_source** добавляет свойства источника данных, к классу или внутри метода. Он используется в сочетании с `db_command` (который принимает *db_source* *имя* параметра в виде его *source_name* параметр).

Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс \_ *Имя_вашего_класса*метод доступа, где *Имя_вашего_класса* — это имя, присвоенное класс, компилятор также создаст класс с именем *Имя_вашего_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.

Пример того, этот атрибут, используемый в приложении, см. в примерах [AtlAgent](https://github.com/Microsoft/VCSamples) и [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="example"></a>Пример

В этом примере вызывает **db_source** для класса, чтобы создать подключение к источнику данных `ds` с помощью базы данных Northwind. `ds` является дескриптором для источника данных, который используется внутренне в `CMyCommand` класса.

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")  
]
class CMyCommand {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**, член, метод, локальный|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)  
