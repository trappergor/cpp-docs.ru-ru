---
title: rename (#import)
ms.date: 10/18/2018
f1_keywords:
- Rename
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 0fbed04f040a47b5b389f40eeb15254da4a7940b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037071"
---
# <a name="rename-import"></a>переименовать (\#импорт)

**Конкретных C++**

Обходит проблемы конфликтов имен.

## <a name="syntax"></a>Синтаксис

```
rename("OldName","NewName")
```

### <a name="parameters"></a>Параметры

*OldName*<br/>
Старое имя в библиотеке типов.

*NewName*<br/>
Имя, используемое вместо старого имени.

## <a name="remarks"></a>Примечания

Если этот атрибут указан, компилятор заменяет все вхождения *OldName* в библиотеку типов с помощью определяемых пользователем *NewName* в результирующих файлах заголовка.

Этот атрибут может использоваться, если имя в библиотеке типов совпадает с определением макроса в системных файлах заголовка. Если это проблема не устранена, то будет создано различные синтаксические ошибки, такие как [Ошибка компилятора C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) и [Ошибка компилятора C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Замена предоставляется для имени, используемого в библиотеке типов, а не для имени, используемого в открывшемся файле заголовка.

Например, предположим, что свойство `MyParent` существует в библиотеке типов, а макрос `GetMyParent` определен в файле заголовка и используется перед `#import`. Так как `GetMyParent` является имя по умолчанию функции-оболочки для обработки ошибок `get` свойство, возникнет конфликт имен. Для решения проблемы используйте следующий атрибут в инструкции `#import`:

```cpp
rename("MyParent","MyParentX")
```

чтобы переименовать имя `MyParent` в библиотеке типов. Попытка переименовать программу-оболочку `GetMyParent` завершится ошибкой:

```cpp
rename("GetMyParent","GetMyParentX")
```

Это происходит потому, что имя `GetMyParent` может возникать только в открывшемся файле заголовка библиотеки типов.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)