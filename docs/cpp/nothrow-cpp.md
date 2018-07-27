---
title: nothrow (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 01/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7efbd22c846327c5731cf3ab14ba1f2045c8636f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939153"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Блок, относящийся только к системам Microsoft**

Объект **__declspec** расширенный атрибут, который может использоваться в объявлении функции.

## <a name="syntax"></a>Синтаксис  
  
> *тип возвращаемой* __declspec(nothrow) [*соглашение вызова*] *имя функции* ([*список аргументов*])

## <a name="remarks"></a>Примечания

Мы рекомендуем использовать новую программу [noexcept](noexcept-cpp.md) оператор вместо `__declspec(nothrow)`.

Этот атрибут сообщает компилятору, что и объявленная функция, и функции, которые она вызывает, никогда не создают исключений. Тем не менее она не обеспечивает директивы. Другими словами, никогда не вызывает [std::terminate](../standard-library/exception-functions.md#terminate) должен быть вызван, в отличие от `noexcept`, или в **std: c ++ 17** режима (Visual Studio 2017 версии 15.5 и более поздние версии), `throw()`.

Поскольку по умолчанию теперь используется модель синхронной обработки исключений, то компилятор может исключить механизм, позволяющий отслеживать время существования удаляемых объектов в такой функции, и значительно уменьшить объем кода. Учитывая следующую директиву препроцессора, три объявления функций эквивалентны в **/std: c ++ 14** режиме:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

В **/std: c ++ 17** режиме `throw()` не эквивалентен других, использующих `__declspec(nothrow)` так как вызывает `std::terminate` должен быть вызван, если исключение из функции.

`void __stdcall f3() throw();` Объявлении используется синтаксис, определенный стандартом C++. В C ++ 17 `throw()` ключевое слово был объявлен устаревшим.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[Ключевые слова](../cpp/keywords-cpp.md)  
