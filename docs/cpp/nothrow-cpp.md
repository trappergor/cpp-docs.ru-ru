---
title: "nothrow (C++) | Документы Microsoft"
ms.custom: 
ms.date: 01/03/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: nothrow_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e0f5f40fbcfcb95952fd956060801e862e9cdaf
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="nothrow-c"></a>nothrow (C++)

**Блок, относящийся только к системам Microsoft**

Расширенный атрибут `__declspec`, который может быть использован в объявлении функций.

## <a name="syntax"></a>Синтаксис  
  
> *Тип возвращаемого значения* __declspec(nothrow) [*соглашение вызова*] *имя функции* ([*список аргументов*])

## <a name="remarks"></a>Примечания

Мы рекомендуем использовать новую программу [noexcept](noexcept-cpp.md) оператор вместо `__declspec(nothrow)`.

Этот атрибут сообщает компилятору, что и объявленная функция, и функции, которые она вызывает, никогда не создают исключений. Тем не менее не обеспечивают директивы. Другими словами, никогда не вызывает [std::terminate](../standard-library/exception-functions.md#terminate) вызываемую, в отличие от `noexcept`, или в **std:c ++ 17** режима (Visual Studio 2017 г 15,5 и более поздних версий), `throw()`.

Поскольку по умолчанию теперь используется модель синхронной обработки исключений, то компилятор может исключить механизм, позволяющий отслеживать время существования удаляемых объектов в такой функции, и значительно уменьшить объем кода. Учитывая следующую директиву препроцессора, три объявления функций эквивалентны в **/std: c ++ 14** режим:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

В **/std: c ++ 17** режиме `throw()` не эквивалентен других пользователей `__declspec(nothrow)` потому, что вынуждает `std::terminate` вызываемый, если исключение из функции.

`void __stdcall f3() throw();` Объявлении используется синтаксис, определенный стандартом C++. В C ++ 17 `throw()` ключевое слово устарела.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[Ключевые слова](../cpp/keywords-cpp.md)  
