---
title: Классы и структуры (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9863786e5e017b69217f984e3aa6d1db597e74d3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864919"
---
# <a name="classes-and-structs--c-component-extensions"></a>Классы и структуры (расширения компонентов C++)
Объявляет класс или структура которого *время существования объекта* администрируется автоматически. Когда объект больше не доступен или выходит за пределы области, Visual C++ автоматически отменяет память, выделенную для этого объекта.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Синтаксис**  
  
```  
  
      class_access  
      ref class  
      name  
      modifier :  inherit_accessbase_type {};  
class_accessref structnamemodifier :  inherit_accessbase_type {};  
class_accessvalue classnamemodifier :  inherit_accessbase_type {};  
class_accessvalue structnamemodifier :  inherit_accessbase_type {};  
  
```  
  
 **Параметры**  
  
 *class_access* (необязательно)  
 Доступность класса или структуры вне сборки. Возможными значениями являются **открытый** и `private` (`private` значение по умолчанию). Вложенные классы и структуры не могут иметь *class_access* спецификатор.  
  
 *name*  
 Имя класса или структуры.  
  
 *модификатор* (необязательно)  
 [Абстрактный](../windows/abstract-cpp-component-extensions.md) и [запечатанный](../windows/sealed-cpp-component-extensions.md) Допустимые модификаторы.  
  
 *inherit_access* (необязательно)  
 Доступность `base_type`. Единственная разрешенная доступность — `public` (`public` — значение по умолчанию).  
  
 *base_type* (необязательно)  
 Базовый тип. Однако тип значения не может действовать как базовый тип.  
  
 Дополнительные сведения см. в описаниях конкретного языка в среды выполнения Windows и общий язык Runtimesections этого параметра.  
  
 **Заметки**  
  
 Доступность членов по умолчанию объекта, объявленного с **ссылочного класса** или **класса значений** — `private`. И доступность по умолчанию членов объекта, объявленных с **структура ссылки** или **структура значения** — `public`.  
  
 Если ссылочный тип наследует от другого ссылочного типа, виртуальные функции в базовом классе необходимо явно переопределить (с [переопределить](../windows/override-cpp-component-extensions.md)) или скрыть (с [new (новый слот в vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). Функции производного класса должны также быть явно помечены как `virtual`.  
  
 Для обнаружения во время компиляции, является ли тип `ref class` или `ref struct`, или `value class` или `value struct`, используйте `__is_ref_class (type)`, `__is_value_class (type)`, или `__is_simple_value_class (type)`. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Дополнительные сведения о классах и структурах см. в разделе  
  
-   [Создание экземпляров классов и структур](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
 
  
-   [Семантика стека C++ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Классы, структуры и объединения](../cpp/classes-and-structs-cpp.md)  
  
-   [Деструкторы и методы завершения в разделе: определение и использование классов и структур (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [Пользовательские операторы (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Заданные пользователем преобразования (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Практическое руководство. Создание программы-оболочки собственного класса для использования в C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Универсальные классы (C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 **Заметки**  
  
 В разделе [классы и структуры ссылки](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) и [классы и структуры значений](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Параметры**  
  
 *base_type* (необязательно)  
 Базовый тип. `ref class` или `ref struct` может наследовать от произвольного числа (включая 0) интерфейсов и от ноля или одного типа `ref`. `value class` или `value struct` может наследовать только от произвольного числа (включая 0) интерфейсов.  
  
 Если объект объявлен с помощью ключевых слов `ref class` или `ref struct`, он доступен дескриптору объекта, то есть указателю счетчика ссылок на объект. Если объявленная переменная выходит за пределы области, компилятор автоматически удаляет базовый объект. Когда объект используется в качестве параметра в вызове или хранится в переменной, фактически передается или хранится только его дескриптор.  
  
 При объявлении объекта с помощью ключевых слов `value class` или `value struct` время жизни объявленного объекта не контролируется. Этот объект аналогичен любому другому стандартному классу или структуре C++.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 В следующей таблице перечислены отличия от синтаксиса, показанного в **все среды выполнения** , характерные для C + +/ CLI.  
  
 **Параметры**  
  
 *base_type* (необязательно)  
 Базовый тип. `ref class` или `ref struct` может наследовать от произвольного числа (включая 0) управляемых интерфейсов и от ноля или одного типа ссылки. `value class` или `value struct` может наследовать только от произвольного числа (включая 0) управляемых интерфейсов.  
  
 Ключевые слова `ref class` и `ref struct` сообщают компилятору, что класс или структура должны выделяться в куче. Когда объект используется в качестве параметра в вызове или хранится в переменной, фактически передается или хранится только ссылка на него.  
  
 `value class` И `value struct` ключевые слова сообщает компилятору, что значение выделенного класса или структуры передается функциям или сохраняется в членах.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)