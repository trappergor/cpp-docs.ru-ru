---
title: режим работы (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 38bfbe025c92aa54956a165367b367cecc6160b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="functional-stlclr"></a>functional (STL/CLR)
Включать заголовок STL/CLR `<cliext/functional>` для определения несколько классов шаблонов и функции и делегаты связанных шаблонов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <functional>  
```  
  
## <a name="declarations"></a>Объявления  
  
|делегат|Описание|  
|--------------|-----------------|  
|[binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)|Делегат с двумя аргументами.|  
|[binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)|Делегат с двумя аргументами возвращающий `void`.|  
|[unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)|Делегат, один аргумент.|  
|[unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)|Один аргумент делегат возвращающий `void`.|  
  
|Класс|Описание|  
|-----------|-----------------|  
|[binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)|Функтор, преобразуемая в отрицательную функтор двумя аргументами.|  
|[binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)|Функтор для привязки к функтор двух аргументов первый аргумент.|  
|[binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)|Функтор второй аргумент привязывается функтор двумя аргументами.|  
|[divides (STL/CLR)](../dotnet/divides-stl-clr.md)|Разделите функтор.|  
|[equal_to (STL/CLR)](../dotnet/equal-to-stl-clr.md)|Равно функтора сравнения.|  
|[greater (STL/CLR)](../dotnet/greater-stl-clr.md)|Больше функтора сравнения.|  
|[greater_equal (STL/CLR)](../dotnet/greater-equal-stl-clr.md)|Функтора сравнения больше или равно.|  
|[less (STL/CLR)](../dotnet/less-stl-clr.md)|Меньше функтора сравнения.|  
|[less_equal (STL/CLR)](../dotnet/less-equal-stl-clr.md)|Функтора сравнения меньше или равно.|  
|[logical_and (STL/CLR)](../dotnet/logical-and-stl-clr.md)|Логическое AND функтор.|  
|[logical_not (STL/CLR)](../dotnet/logical-not-stl-clr.md)|Логическое не функтор.|  
|[logical_or (STL/CLR)](../dotnet/logical-or-stl-clr.md)|Функтор логического или.|  
|[minus (STL/CLR)](../dotnet/minus-stl-clr.md)|Вычитание функтор.|  
|[modulus (STL/CLR)](../dotnet/modulus-stl-clr.md)|Функтор остатка от деления.|  
|[multiplies (STL/CLR)](../dotnet/multiplies-stl-clr.md)|Умножьте функтор.|  
|[negate (STL/CLR)](../dotnet/negate-stl-clr.md)|Функтор для возвращения аргумента инвертировано.|  
|[not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)|Функтора сравнения не равны.|  
|[plus (STL/CLR)](../dotnet/plus-stl-clr.md)|Добавьте функтор.|  
|[unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)|Функтор, преобразуемая в отрицательную функтор один аргумент.|  
  
|Функция|Описание|  
|--------------|-----------------|  
|[bind1st (STL/CLR)](../dotnet/bind1st-stl-clr.md)|Создает binder1st функтор и аргумента.|  
|[bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)|Создает binder2nd функтор и аргумента.|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|Создает unary_negate для функтором.|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|Создает binary_negate для функтором.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)