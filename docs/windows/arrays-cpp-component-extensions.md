---
title: "Массивы (расширения компонентов C++) | Microsoft Docs"
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
  - "cli::array"
  - "details::array"
  - "lang::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array - ключевое слово [C++]"
  - "массивы [C++]"
  - "массивы [C++], многомерные"
  - "объявление массивов, сведения об объявлении массивов"
  - "многомерные массивы"
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Массивы (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип `Platform::Array<T>` в [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] или ключевое слово `array` в [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] объявляет массив указанного типа и начальное значение.  
  
## Все платформы  
 Массив должен быть объявлен с помощью модификатора дескриптора объекта \(^\) после закрывающей угловой скобки \(\>\) в объявлении.  
  
 Количество элементов массива не является частью типа.  Одна переменная массива может ссылаться на массивы различных размеров.  
  
 В отличие от стандартного C\+\+, индексация не является синонимом арифметических операций над указателями и не коммутативна.  
  
 Дополнительные сведения о массивах см.:  
  
-   [Ковариация массивов](../misc/array-covariance.md)  
  
-   [Практическое руководство. Использование массивов в C\+\+\/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
  
-   [Практическое руководство. Создание многомерных массивов](../misc/how-to-create-multidimension-arrays.md)  
  
-   [Практическое руководство. Создание массивов из управляемых массивов \(неравномерные массивы\)](../misc/how-to-create-arrays-of-managed-arrays-jagged-arrays.md)  
  
-   [Практическое руководство. Создание Typedefs для управляемых архивов](../misc/how-to-make-typedefs-for-managed-arrays.md)  
  
-   [Практическое руководство. Использование управляемых массивов в качестве параметров типа шаблона](../misc/how-to-use-managed-arrays-as-template-type-parameters.md)  
  
-   [Списки аргументов переменных \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
-   [Практическое руководство. Сортировка массивов](../misc/how-to-sort-arrays.md)  
  
-   [Практическое руководство. Сортировка массивов с помощью настраиваемых условий](../misc/how-to-sort-arrays-using-custom-criteria.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Массивы являются членами пространства имен `Platform`.  Массивы могут быть только одномерными.  
  
 **Синтаксис**  
  
 В первом примере синтаксиса используется агрегатное ключевое слово `ref new`, чтобы выделить память для массива.  Во втором примере объявляется локальный массив.  
  
```  
  
        [qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = ref new [Platform::]Array< initialization-type > [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \(необязательно\)  
 Один или несколько следующих спецификаторов класса хранения: [mutable](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [static](../misc/static-cpp.md).  
  
 `array-type`  
 Тип переменной массива.  Допустимыми типами являются основные типы и классы [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], ссылочные классы и структуры, классы и структуры значений и собственные указатели \(`type``*`\).  
  
 `rank` \(необязательно\)  
 Число измерений в массиве.  Должно быть равно 1.  
  
 `identifier`  
 Имя переменной массива.  
  
 `initialization-type`  
 Тип значений, которые инициализируют массив.  Как правило, `array-type` и `initialization-type` принадлежат к одному и тому же типу.  Однако типы могут быть разными, если существует преобразование из `initialization-type` в `array-type`— например, если `initialization-type` является производным от `array-type`.  
  
 `initialization-list` \(необязательно\)  
 Список в фигурных скобках из значений, разделенных запятыми, инициализирует элементы массива.  Например, если `rank-size-list` был равен `(3)`, что объявляет одномерный массив из 3 элементов, `initialization list` может быть таким `{1,2,3}`.  
  
 **Примечания**  
  
 Во время компиляции можно определить, является ли тип массивом с подсчетом ссылок, с помощью `__is_ref_array(``type``)`.  Для получения дополнительной информации см. [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
### Примеры  
 В следующем примере создается одномерный массив из 100 элементов.  
  
```  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Синтаксис**  
  
 В первом примере синтаксиса используется ключевое слово `gcnew`, чтобы выделить память для массива.  Во втором примере объявляется локальный массив.  
  
```  
  
        [qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = gcnew [cli::]array< initialization-type [,rank] >(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \(необязательно\)  
 Один или несколько следующих спецификаторов класса хранения: [mutable](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [static](../misc/static-cpp.md).  
  
 `array-type`  
 Тип переменной массива.  Допустимыми типами являются основные типы и классы [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], ссылочные классы и структуры, классы и структуры значений и собственные указатели \(`type``*`\) и собственные типы POD.  
  
 `rank` \(необязательно\)  
 Число измерений в массиве.  Значение по умолчанию — 1; максимальное число — 32.  Каждое измерение массива само является массивом.  
  
 `identifier`  
 Имя переменной массива.  
  
 `initialization-type`  
 Тип значений, которые инициализируют массив.  Как правило, `array-type` и `initialization-type` принадлежат к одному и тому же типу.  Однако типы могут быть разными, если существует преобразование из `initialization-type` в `array-type`— например, если `initialization-type` является производным от `array-type`.  
  
 `rank-size-list`  
 Список размеров каждого измерения массива, разделенный запятыми.  Также, если задан параметр `initialization-list`, компилятор может определить размер каждого измерения, и `rank-size-list` можно опустить.  Для получения дополнительной информации см. [Практическое руководство. Создание многомерных массивов](../misc/how-to-create-multidimension-arrays.md).  
  
 `initialization-list` \(необязательно\)  
 Список в фигурных скобках из значений, разделенных запятыми, инициализирует элементы массива.  Или разделенный запятыми список вложенных элементов *initialization\-list*, который инициализирует элементы в многомерном массиве.  
  
 Например, если `rank-size-list` был равен `(3)`, что объявляет одномерный массив из 3 элементов, `initialization list` может быть таким `{1,2,3}`.  Если `rank-size-list` был равен `(3,2,4)`, что объявляет трехмерный массив с 3 элементами в первом измерении, 2 элементами во втором и 4 элементами в третьем, `initialization-list` может быть таким `{{1,2,3},{0,0},{-5,10,-21,99}}`.  
  
 **Примечания**  
  
 `array` находится в пространстве имен [Пространства имен Platform, default и cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Как и в стандартном C\+\+, индексы массива начинаются от нуля, и массив индексируется с помощью квадратных скобок \(\[\]\).  В отличие от стандартного C\+\+, индексы многомерного массива указываются в списке индексов каждого измерения вместо набора операторов квадратных скобок \(\[\]\) для каждого измерения.  Например, *identifier*\[*index1*, *index2*\] вместо *identifier*\[*index1*\]\[*index2*\].  
  
 Все управляемые массивы являются производными от `System::Array`.  Любой метод или свойство `System::Array` может применяться непосредственно к переменной массива.  
  
 При создании массива указателей на управляемый класс элементы массива инициализируются нулем.  
  
 При создании массива, тип элементов которого является типом значения `V`, к каждому элементу массива применяется конструктор по умолчанию для `V`.  Для получения дополнительной информации см. [Эквиваленты собственным типам C\+\+ в .NET Framework](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Во время компиляции, можно определить, является ли тип массивом среды CLR с помощью `__is_ref_array(``type``)`.  Для получения дополнительной информации см. [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 В следующем примере создается одномерный массив из 100 элементов, и трехмерный массив с 3 элементами в первом измерении, 5 элементами во втором и 6 элементами в третьем.  
  
```  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)