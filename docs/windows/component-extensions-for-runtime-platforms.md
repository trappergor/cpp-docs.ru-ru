---
title: "Расширения компонентов для платформ среды выполнения | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ключевые слова [C++]"
  - "Управляемые расширения для C++, синтаксис замены"
  - "Visual C++, ключевые слова"
  - "новые возможности [C++], ключевые слова"
  - "новые возможности [C++], возможности языка"
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 77
caps.handback.revision: 77
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Расширения компонентов для платформ среды выполнения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ предоставляет расширения языка, помогающие при программировании для различных платформ.  С помощью [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) можно программировать приложения и компоненты [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], компилируемые в машинный код.  Хотя приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] можно создавать путем программирования непосредственно для интерфейсов модели COM [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] с помощью [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)], можно также работать с конструкторами, исключениями и другими современными идиомами программирования C\+\+.  Для программирования на C\+\+ в управляемой среде выполнения в платформе .NET можно использовать [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  
  
 **Две среды выполнения, один набор расширений**  
  
 [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] является подмножеством [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  Для общих расширений [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] и [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] семантика зависит от ориентации на среду CLR или [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Чтобы скомпилировать приложение для запуска в [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], укажите параметр компилятора **\/ZW**.  Чтобы скомпилировать приложение для запуска в среде CLR, задайте параметр компилятора **\/clr**.  Если для создания проекта используется Visual Studio, эти параметры устанавливаются автоматически.  
  
 Дополнительные сведения о создании приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] на C\+\+ см. в разделе [Схема создания приложений с помощью C\+\+](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] расширяет стандарт ISO\/ANSI C\+\+ и определяется стандартом Ecma [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  Дополнительные сведения см. в статье [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
## Ключевые слова типов данных  
 Расширения языка содержат *агрегатные ключевые слова*. Это ключевые слова, состоящие из двух токенов, разделенных пробелом.  Когда токены используются отдельно, они могут иметь одно значение, а при использовании вместе — другое значение.  Например, ключевое слово "ref" — это обычный идентификатор, а слово "class" — ключевое слово, объявляющее собственный класс.  Однако при объединении этих слов в строку `ref class` полученное агрегатное ключевое слово объявляет сущность, называемую *классом среды выполнения*.  
  
 Расширения также содержат *контекстно\-зависимые* ключевые слова.  Ключевое слово рассматривается как контекстно\-зависимое на основе типа содержащего его оператора и размещения в нем.  Например, токен "property" может быть идентификатором или может объявлять специальный тип открытого члена класса.  
  
 В следующей таблице перечислены ключевые слова в расширении языка C\+\+.  
  
|Ключевое слово|Контекстно\-зависимое?|Назначение|Ссылка|  
|--------------------|----------------------------|----------------|------------|  
|`ref class`<br /><br /> `ref struct`|Нет|Объявляет класс.|[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|Нет|Объявляет класс значения.|[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|Нет|Объявляет интерфейс.|[interface class](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|Нет|Объявляет перечисление.|[класс перечисления](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|Да|Объявляет свойство.|[property](../windows/property-cpp-component-extensions.md)|  
|`delegate`|Да|Объявляет делегат.|[delegate](../windows/delegate-cpp-component-extensions.md)|  
|`event`|Да|Объявление события.|[event](../windows/event-cpp-component-extensions.md)|  
  
## Спецификаторы переопределения  
 Для указания поведения переопределения при наследовании можно использовать указанные ниже ключевые слова.  Хотя ключевое слово `new` не является расширением C\+\+, оно перечислено ниже, поскольку его можно использовать в дополнительном контексте.  Некоторые спецификаторы также допустимы для машинного программирования.  Дополнительные сведения см. в разделе [Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
|Ключевое слово|Контекстно\-зависимое?|Назначение|Ссылка|  
|--------------------|----------------------------|----------------|------------|  
|`abstract`|Да|Указывает, что функции или классы являются абстрактными.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|Нет|Указывает, что функция не является переопределением версии базового класса.|[new \(новый слот в vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|Да|Указывает, что метод должен быть переопределением версии базового класса.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|Да|Предотвращает использование классов в качестве базовых классов.|[запечатанные](../windows/sealed-cpp-component-extensions.md)|  
  
## Ключевые слова для универсальных шаблонов  
 Указанные ниже ключевые слова добавлены для поддержки универсальных типов.  Дополнительные сведения см. в разделе [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md).  
  
|Ключевое слово|Контекстно\-зависимое?|Цель|  
|--------------------|----------------------------|----------|  
|`generic`|Нет|Объявляет универсальный тип.|  
|`where`|Да|Определяет ограничения, применяемые к параметру универсального типа.|  
  
## Прочие ключевые слова  
 В расширения C\+\+ добавлены следующие ключевые слова.  
  
|Ключевое слово|Контекстно\-зависимое?|Назначение|Ссылка|  
|--------------------|----------------------------|----------------|------------|  
|`finally`|Да|Указывает поведение обработки исключений по умолчанию.|[Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|Нет|Перечисляет элементы коллекции.|[for each, in](../dotnet/for-each-in.md)|  
|`gcnew`|Нет|Выделяет типы в куче со сбором мусора.  Используйте вместо `new` и `delete`.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|Да|Выделяет тип [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Используйте вместо `new` и `delete`.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|Да|Указывает, что член можно инициализировать только в объявлении или в статическом конструкторе.|[initonly](../dotnet/initonly-cpp-cli.md)|  
|`literal`|Да|Создает переменную литерала.|[literal](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|Нет|Означает, что обработчик или указатель не указывает на объект.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## Конструкции шаблонов  
 Перечисленные ниже языковые конструкции реализуются в виде шаблонов, а не ключевых слов.  При указании параметра компилятора **\/ZW** они определяются в пространстве имен `lang`.  При указании параметра компилятора **\/clr** они определяются в пространстве имен `cli`.  
  
|Ключевое слово|Назначение|Ссылка|  
|--------------------|----------------|------------|  
|`array`|Объявляет массив.|[Массивы](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|\(Только для среды CLR\). Указывает на данные в ссылочном типе.|[interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|\(Только для среды CLR\). Указывает на ссылочные типы среды CLR, чтобы временно отключить систему сборки мусора.|[pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md)|  
|`safe_cast`|Определяет и выполняет оптимальный метод приведения для типа среды выполнения.|[safe\_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|\(Только для среды CLR\). Извлекает объект <xref:System.Type?displayProperty=fullName>, описывающий заданный тип или объект.|[typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)|  
  
## Деклараторы  
 Следующие деклараторы типа указывают среде выполнения на необходимость автоматически управлять временем существования и удалением выделенных объектов.  
  
|Оператор|Назначение|Ссылка|  
|--------------|----------------|------------|  
|`^`|Объявляет дескриптор объекта, то есть указатель на объект [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] или CLR, который автоматически удаляется, если больше не используется.|[Оператор дескриптора объекта \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|Объявляет отслеживаемую ссылку, то есть ссылку на объект [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] или CLR, который автоматически удаляется, если больше не используется.|[Оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## Дополнительные конструкции и связанные разделы  
 В этом разделе перечислены дополнительные программные конструкции и разделы, относящиеся к среде CLR.  
  
|Раздел|Описание|  
|------------|--------------|  
|[\_\_identifier \(C\+\+\/CLI\)](../windows/identifier-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и среда CLR\). Разрешает использование ключевых слов в качестве идентификаторов.|  
|[Списки аргументов переменных \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и среда CLR\). Разрешает функции принимать переменное число аргументов.|  
|[Эквиваленты собственным типам C\+\+ в .NET Framework](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|Перечисляет типы среды CLR, используемые вместо целочисленных типов C\+\+.|  
|Модификатор [appdomain](../Topic/appdomain.md) `__declspec`|Модификатор `__declspec`, требующий, чтобы статические и глобальные переменные существовали для каждого домена приложений.|  
|[Приведение в стиле C с использованием параметра \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)|Описывается интерпретация приведений в стиле C.|  
|Соглашение о вызове [\_\_clrcall](../cpp/clrcall.md)|Указывается соглашение о вызовах, совместимое со средой CLR.|  
|`__cplusplus_cli`|[Предустановленный макрос](../preprocessor/predefined-macros.md)|  
|[Custom Attributes](../windows/custom-attributes-cpp.md)|Описывается определение собственных атрибутов среды CLR.|  
|[Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)|Общие сведения об обработке исключений.|  
|[Явные переопределения](../windows/explicit-overrides-cpp-component-extensions.md)|Демонстрируется переопределение произвольных членов функциями\-членами.|  
|[Дружественные сборки \(C\+\+\)](../dotnet/friend-assemblies-cpp.md)|Описывается доступ клиентской сборки ко всем типам в компоненте сборки.|  
|[Упаковка\-преобразование](../windows/boxing-cpp-component-extensions.md)|Описываются условия, при которых упаковываются типы значений.|  
|[Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Описывается выявление характеристик типов во время компиляции.|  
|Директивы pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md)|Демонстрируется сосуществование управляемых и неуправляемых функций в одном модуле.|  
|Модификатор [процесс](../cpp/process.md) `__declspec`|Модификатор `__declspec`, требующий, чтобы статические и глобальные переменные существовали для каждого процесса.|  
|[Отражение](../dotnet/reflection-cpp-cli.md)|Демонстрируется CLR\-версия данных типа во время выполнения.|  
|[String](../windows/string-cpp-component-extensions.md)|Описывается преобразование компилятором строковых литералов в объект <xref:System.String>.|  
|[Перенаправление типов \(C\+\+\/CLI\)](../windows/type-forwarding-cpp-cli.md)|Разрешает перемещение типа из поставляемой сборки в другую сборку, чтобы исключить необходимость повторной компиляции клиентского кода.|  
|[Пользовательские атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md)|Демонстрируются атрибуты, определяемые пользователем.|  
|[Директива \#using](../preprocessor/hash-using-directive-cpp.md)|Импортирует внешние сборки.|  
|[Документация XML](../ide/xml-documentation-visual-cpp.md)|Пояснения к документации по XML\-коду с использованием [\/doc \(обработка комментариев документации\)](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
  
## См. также  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)