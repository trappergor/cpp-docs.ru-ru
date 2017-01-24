---
title: "Классы и структуры (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "public"
  - "ref struct"
  - "value_CPP"
  - "ref class"
  - "value struct"
  - "ref struct_cpp"
  - "ref class_cpp"
  - "value class_cpp"
  - "value struct_cpp"
  - "value class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref class - ключевое слово [C++]"
  - "ref struct - ключевое слово [C++]"
  - "value class - ключевое слово [C++]"
  - "value struct - ключевое слово [C++]"
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы и структуры (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объявляет класс или структуру, чье *время жизни объекта* администрируется автоматически.  Когда объект больше не доступен или выходит за пределы области, Visual C\+\+ автоматически отменяет память, выделенную для этого объекта.  
  
## Все среды выполнения  
 **Синтаксис**  
  
```  
  
          class_access ref class    name modifier :  inherit_access base_type {};  
class_access ref struct   name modifier :  inherit_access base_type {};  
class_access value class  name modifier :  inherit_access base_type {};  
class_access value struct name modifier :  inherit_access base_type {};  
  
```  
  
 **Параметры**  
  
 *class\_access* \(необязательно\)  
 Доступность класса или структуры вне сборки.  Возможные значения: **public** и `private` \(`private` — значение по умолчанию\).  Вложенные классы и структуры не могут иметь описатель *class\_access*.  
  
 *имя*  
 Имя класса или структуры.  
  
 *modifier* \(необязательно\)  
 Допустимые модификаторы — [abstract](../windows/abstract-cpp-component-extensions.md) и [sealed](../windows/sealed-cpp-component-extensions.md).  
  
 *inherit\_access* \(необязательно\)  
 Доступность `base_type`.  Единственная разрешенная доступность — `public` \(`public` — значение по умолчанию\).  
  
 *base\_type* \(необязательно\)  
 Базовый тип.  Однако тип значения не может действовать как базовый тип.  
  
 Дополнительные сведения см. в описаниях этого параметра для конкретного языка в разделах [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)].  
  
 **Примечания**  
  
 Доступность по умолчанию членов объекта, объявленного с помощью **класса ссылки** или **класса значений**, — `private`.  Доступность по умолчанию членов объекта, объявленного с помощью **структуры ссылки** или **структуры значений**, — `public`.  
  
 Когда ссылочный тип наследует от другого ссылочного типа, виртуальные функции в базовом классе необходимо явно переопределить \(с помощью [override](../windows/override-cpp-component-extensions.md)\) или скрыть \(с помощью [new \(новый слот в vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)\).  Функции производного класса должны также быть явно помечены как `virtual`.  
  
 Для обнаружения во время компиляции того, является ли тип `ref class` или `ref struct` либо `value class` или `value struct`, используйте `__is_ref_class (``type``)`, `__is_value_class (``type``)` или  `__is_simple_value_class (``type``)`.  Дополнительные сведения см. в разделе [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Дополнительные сведения о классах и структурах см. в разделе  
  
-   [Создание экземпляров классов и структур](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [Семантика указателя this в типах значений и ссылочных типах](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md)  
  
-   [Семантика стека C\+\+ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [Классы, структуры и объединения](../Topic/Classes%20and%20Structs%20\(C++\).md)  
  
-   [открытые и закрытые члены в собственных классах](../misc/how-to-declare-public-and-private-on-native-classes.md)  
  
-   [Неявно абстрактные классы](../misc/implicitly-abstract-classes.md)  
  
-   [Определение статических конструкторов в классе или структуре](../misc/how-to-define-static-constructors-in-a-class-or-struct.md)  
  
-   [Конструктор копии может не создаваться](../Topic/Copy%20Constructor%20May%20Not%20Be%20Generated.md)  
  
-   [Функции со скрываемой сигнатурой в ссылочных типах](../misc/hide-by-signature-functions-in-reference-types.md)  
  
-   [Деструкторы и методы завершения в Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md)  
  
-   [Видимость типов и членов](../Topic/Type%20and%20Member%20Visibility.md)  
  
-   [Пользовательские операторы](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [Заданные пользователем преобразования](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [Практическое руководство. Создание программы\-оболочки для неуправляемого класса для использования в языке C\#](../Topic/How%20to:%20Wrap%20Native%20Class%20for%20Use%20by%20C%23.md)  
  
-   [Универсальные классы \(C\+\+\/CLI\)](../Topic/Generic%20Classes%20\(C++-CLI\).md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
 См. разделы [Классы и структуры ссылки \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) и [Классы и структуры значений \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx).  
  
 **Параметры**  
  
 *base\_type* \(необязательно\)  
 Базовый тип.  `ref class` или `ref struct` может наследовать от произвольного числа \(включая 0\) интерфейсов и от ноля или одного типа `ref`.  `value class` или `value struct` может наследовать только от произвольного числа \(включая 0\) интерфейсов.  
  
 Если объект объявлен с помощью ключевых слов `ref class` или `ref struct`, он доступен дескриптору объекта, то есть указателю счетчика ссылок на объект.  Если объявленная переменная выходит за пределы области, компилятор автоматически удаляет базовый объект.  Когда объект используется в качестве параметра в вызове или хранится в переменной, фактически передается или хранится только его дескриптор.  
  
 При объявлении объекта с помощью ключевых слов `value class` или `value struct` время жизни объявленного объекта не контролируется.  Этот объект аналогичен любому другому стандартному классу или структуре C\+\+.  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 В следующей таблице перечислены отличия от синтаксиса, показанного в разделе **Все среды выполнения**, характерные для C\+\+\/CLI.  
  
 **Параметры**  
  
 *base\_type* \(необязательно\)  
 Базовый тип.  `ref class` или `ref struct` может наследовать от произвольного числа \(включая 0\) управляемых интерфейсов и от ноля или одного типа ссылки.  `value class` или `value struct` может наследовать только от произвольного числа \(включая 0\) управляемых интерфейсов.  
  
 Ключевые слова `ref class` и `ref struct` сообщают компилятору, что класс или структура должны выделяться в куче.  Когда объект используется в качестве параметра в вызове или хранится в переменной, фактически передается или хранится только ссылка на него.  
  
 Ключевые слова `value class` и `value struct` указывают компилятору, что значение выделенного класса или структуры передается функциям или сохраняется в членах.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)