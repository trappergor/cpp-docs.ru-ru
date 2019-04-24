---
title: Оператор __uuidof
ms.date: 10/10/2018
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
ms.openlocfilehash: a14ef9043ec2196ff930a37d0eff95e90024d3d5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769203"
---
# <a name="uuidof-operator"></a>Оператор __uuidof

**Блок, относящийся только к системам Microsoft**

Извлекает идентификатор GUID, присоединенный к выражению.

## <a name="syntax"></a>Синтаксис

```
__uuidof (expression)
```

## <a name="remarks"></a>Примечания

*Выражение* может быть имя типа, указатель, ссылку или массив этого типа, шаблон, специализированный для этого типа, или переменную этого типа. Этот аргумент является допустимым, если компилятор может использовать его для поиска прикрепленного GUID.

Является особым случаем этой встроенной функции, когда либо **0** или указано значение NULL в качестве аргумента. В этом случае **__uuidof** Возвращает GUID, состоящий из нулей.

Это ключевое слово позволяет извлечь GUID, прикрепленный к следующим объектам:

- Объект [uuid](../cpp/uuid-cpp.md) расширенный атрибут.

- Блок библиотеки, созданный с помощью [модуль](../windows/attributes/module-cpp.md) атрибута.

> [!NOTE]
> В отладочной сборке **__uuidof** всегда инициализирует объект динамически (во время выполнения). В окончательном построении **__uuidof** можно статически (во время компиляции) инициализировать объект.

Для совместимости с предыдущими версиями **_uuidof** является синонимом **__uuidof** Если параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) — указан.

## <a name="example"></a>Пример

Следующий код (скомпилированный с библиотекой ole32.lib) будет выводить идентификатор uuid для блока библиотеки, созданного с атрибутом module.

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>Комментарии

В случаях, если имя библиотеки больше не находится в области, можно использовать `__LIBID_` вместо **__uuidof**. Пример:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)