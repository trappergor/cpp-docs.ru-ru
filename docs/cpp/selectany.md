---
title: selectany | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- selectany_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee48bf8a739f7fc024604ba178b56da99844861b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102350"
---
# <a name="selectany"></a>selectany

**Блок, относящийся только к системам Microsoft**

Сообщает компилятору, что объявленный элемент глобальных данных (переменная или объект) является универсальным COMDAT (упакованной функцией).

## <a name="syntax"></a>Синтаксис

```
__declspec( selectany ) declarator
```

## <a name="remarks"></a>Примечания

Во время компоновки, если отображается несколько определений COMDAT, компоновщик выбирает один из них и игнорирует остальные. Если параметр компоновщика [предотвратят](../build/reference/opt-optimizations.md) (оптимизации) установлен, а затем происходит исключение COMDAT для удаления всех элементов данных, на которые нет ссылок в выходных данных компоновщика.

Конструкторы и назначение с помощью глобальной функции или статических методов в объявлении не создадут ссылку и не предотвратят исключение /OPT:REF. Побочные эффекты такого кода не должны быть зависимыми, если не существует других ссылок на данные.

Для динамически инициализированных глобальных объектов **selectany** удалит код инициализации объекта без ссылки, а также.

Обычно элемент глобальных данных можно инициализировать только один раз в проекте EXE или DLL. **selectany** может использоваться при инициализации глобальных данных, определенных в заголовках, если одинаковый заголовок отображается в более чем один исходный файл. **selectany** доступен в компиляторах C и C++.

> [!NOTE]
>  **selectany** может применяться только к существующей инициализации элементов глобальных данных, видимых извне.

## <a name="example"></a>Пример

Этот код показан способ использования **selectany** атрибут:

```cpp
//Correct - x1 is initialized and externally visible
__declspec(selectany) int x1=1;

//Incorrect - const is by default static in C++, so
//x2 is not visible externally (This is OK in C, since
//const is not by default static in C)
const __declspec(selectany) int x2 =2;

//Correct - x3 is extern const, so externally visible
extern const __declspec(selectany) int x3=3;

//Correct - x4 is extern const, so it is externally visible
extern const int x4;
const __declspec(selectany) int x4=4;

//Incorrect - __declspec(selectany) is applied to the uninitialized
//declaration of x5
extern __declspec(selectany) int x5;

// OK: dynamic initialization of global object
class X {
public:
X(int i){i++;};
int i;
};

__declspec(selectany) X x(1);
```

## <a name="example"></a>Пример

Этот код показан способ использования **selectany** атрибута, чтобы гарантировать свертывание записей COMDAT при использовании [/OPT: ICF](../build/reference/opt-optimizations.md) параметр компоновщика. Обратите внимание на то, что данные должны быть отмечены **selectany** и помещено в **const** раздел (только для чтения). Раздел, доступный только для чтения, необходимо указать явно.

```cpp
// selectany2.cpp
// in the following lines, const marks the variables as read only
__declspec(selectany) extern const int ix = 5;
__declspec(selectany) extern const int jx = 5;
int main() {
   int ij;
   ij = ix + jx;
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)