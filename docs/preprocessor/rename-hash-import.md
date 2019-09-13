---
title: переименовать атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- Rename
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: ef1f64e0c268f850899efe499f7b1ad3991dd570
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216659"
---
# <a name="rename-import-attribute"></a>переименовать атрибут импорта

**C++Зависящ**

Обходит проблемы конфликтов имен.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **Rename (** "*oldname*" **,** "*newname*" **)**

### <a name="parameters"></a>Параметры

*OldName*\
Старое имя в библиотеке типов.

*NewName*\
Имя, используемое вместо старого имени.

## <a name="remarks"></a>Примечания

Если указан атрибут Rename, компилятор заменяет все вхождения *oldname* в *Type-Library* на предоставляемое пользователем *новое* имя в результирующих файлах заголовков.

Атрибут **Rename** можно использовать, если имя в библиотеке типов совпадает с определением макроса в системных файлах заголовков. Если эта ситуация не устранена, компилятор может выдавать различные синтаксические ошибки, такие как [Ошибка компилятора C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) и [Ошибка компилятора C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Замена предоставляется для имени, используемого в библиотеке типов, а не для имени, используемого в открывшемся файле заголовка.

Например, предположим, что свойство `MyParent` существует в библиотеке типов, а макрос `GetMyParent` определен в файле заголовка и используется перед `#import`. Поскольку `GetMyParent` является именем по умолчанию для функции-оболочки для свойства обработки `get` ошибок, возникнет конфликт имен. Для решения проблемы используйте следующий атрибут в инструкции `#import`:

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

чтобы переименовать имя `MyParent` в библиотеке типов. Попытка переименовать программу-оболочку `GetMyParent` завершится ошибкой:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Это связано с тем, `GetMyParent` что имя встречается только в результирующем файле заголовка библиотеки типов.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
