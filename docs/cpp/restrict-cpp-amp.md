---
title: ограничения (C++ AMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60ac40e2cb64c307574d14c1f7cc7a5290c740ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
Спецификатор ограничения может применяться к объявлениям функций и лямбда-выражений. Он реализует ограничения на код функции и на ее поведение в приложениях, в которых используется среда выполнения C++ AMP.  
  
> [!NOTE]
>  Сведения о `restrict` ключевое слово, которое является частью `__declspec` атрибуты классов хранения в разделе [ограничить](../cpp/restrict.md).  
  
 Предложение `restrict` принимает следующие формы:  
  
|Предложение|Описание:|  
|------------|-----------------|  
|`restrict(cpu)`|В функции могут использоваться все возможности языка C++. Вызывать ее могут только другие функции, объявленные с помощью функции restrict(cpu).|  
|`restrict(amp)`|В функции может использоваться только то подмножество языка C++, выполнение которого может ускорить C++ AMP.|  
|Последовательность функций `restrict(cpu)` и `restrict(amp)`.|Функция должна соблюдать ограничения, устанавливаемые обеими функциями: и `restrict(cpu)`, и `restrict(amp)`. Вызывать ее могут функции, объявленные при помощи `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` или `restrict(amp, cpu)`.<br /><br /> Форма `restrict(A) restrict(B)` может быть записана в виде `restrict(A,B)`.|  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `restrict` является контекстным ключевым словом. Спецификаторы ограничения `cpu` и `amp` не являются зарезервированными словами. Список спецификаторов не может быть расширен. Функция без предложения `restrict` аналогична функции с предложением `restrict(cpu)`.  
  
 Для функции с предложением `restrict(amp)` действуют следующие ограничения:  
  
-   Функция может вызывать только функции с предложением `restrict(amp)`.  
  
-   Функция должна поддерживать подстановку.  
  
-   В функции могут объявляться только переменные типов `int`, `unsigned int`, `float` и `double`, а также классы и структуры, которые содержат только значения указанных типов. Также допускаются значения `bool`, однако если они используются в составном типе, то они должны иметь 4-байтное выравнивание.  
  
-   Лямбда-функции не могут захватывать по ссылке и не могут захватывать указатели.  
  
-   Указатели с одним косвенным обращением и ссылки поддерживаются только как локальные переменные, аргументы функций и типы возвращаемых значений.  
  
-   Следующие возможности не допускаются:  
  
    -   Рекурсия.  
  
    -   Переменные, объявленные с [volatile](../cpp/volatile-cpp.md) ключевое слово.  
  
    -   Виртуальные функции.  
  
    -   Указатели на функции.  
  
    -   Указатели на функции-члены.  
  
    -   Указатели в структурах.  
  
    -   Указатели на указатели.  
  
    -   Операторы `goto`.  
  
    -   Операторы с метками.  
  
    -   Операторы `try`, `catch` и `throw`.  
  
    -   Глобальные переменные.  
  
    -   Статические переменные. Используйте [ключевое слово tile_static](../cpp/tile-static-keyword.md) вместо него.  
  
    -   Приведение типов `dynamic_cast`.  
  
    -   Оператор `typeid`.  
  
    -   Объявления asm.  
  
    -   Использование vararg.  
  
 Обсуждение функции ограничения см. в разделе [restrict(amp) ограничения](http://go.microsoft.com/fwlink/p/?LinkId=251089).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `restrict(amp)`предложения.  
  
```  
  
void functionAmp() restrict(amp) {}   
void functionNonAmp() {}   
  
void callFunctions() restrict(amp)   
{   
    // int is allowed.  
    int x;  
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.  
    // long long int y;   
  
    // Calling an amp-restricted function is allowed.  
    functionAmp();   
  
    // Calling a non-amp-restricted function is not allowed.  
    // functionNonAmp();   
  
}  
```  
  
## <a name="see-also"></a>См. также  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)