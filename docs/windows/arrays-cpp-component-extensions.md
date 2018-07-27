---
title: Массивы (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a17649402fa6ebe9c98d768badcf36e5700f5b75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862726"
---
# <a name="arrays-c-component-extensions"></a>Массивы (расширения компонентов C++)
`Platform::Array<T>` Типа в C + +/ CX, или `array` ключевого слова в C + +/ CLI, объявляет массив указанного типа и начальное значение.  
  
## <a name="all-platforms"></a>Все платформы  
 Массив должен быть объявлен с помощью модификатора дескриптора объекта (^) после закрывающей угловой скобки (>) в объявлении.  
 Количество элементов массива не является частью типа. Одна переменная массива может ссылаться на массивы разных размеров.  
  
 В отличие от стандартной версии C++, индексация не идентична арифметическим операциям над указателями и не коммутативна.  
  
 Дополнительные сведения о массивах см. в следующих разделах:  
  
-   [Практическое руководство. Использование массивов в C++/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [Списки аргументов переменной длины (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Массивы являются членами пространства имен `Platform`. Они могут быть только одномерными.  
  
### <a name="syntax"></a>Синтаксис  
  
 В первом примере синтаксиса используется агрегатное ключевое слово `ref new`, чтобы выделить память для массива. Во втором примере объявляется локальный массив.  
  
```  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *квалификаторы* [необязательно]  
 Один или несколько следующих спецификаторов класса хранения: [изменяемый](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [статический](../cpp/static-members-cpp.md).  
  
 `array-type`  
 Тип переменной массива. Допустимые типы: класса среды выполнения Windows и базовые типы, классы и структуры, классы значений и структуры и собственные указатели (`type*`).  
  
 `rank` [необязательный параметр]  
 Число измерений массива. Должен иметь значение 1.  
  
 `identifier`  
 Имя переменной массива.  
  
 `initialization-type`  
 Тип значений, которые инициализируют массив. Как правило, `array-type` и `initialization-type` относятся к одному и тому же типу. Однако при наличии преобразования из `initialization-type` в `array-type` (например, если `initialization-type` является производным от `array-type`) типы могут быть разными.  
  
 `initialization-list` [необязательный параметр]  
 Разделенный запятыми список инициализирующих элементы массива значений в фигурных скобках. Например если `rank-size-list` были `(3)`, который объявляет одномерный массив из 3 элементов `initialization list` может быть `{1,2,3}`.  
  
### <a name="remarks"></a>Примечания  
  
 Во время компиляции можно определить является ли тип массивом подсчетом ссылок с `__is_ref_array(type)`. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
### <a name="examples"></a>Примеры  
 В следующем примере создается одномерный массив из 100 элементов.  
  
```cpp  
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
  
## <a name="common-language-runtime"></a>Среда CLR 
  
### <a name="syntax"></a>Синтаксис  
  
 В первом примере синтаксиса используется ключевое слово `gcnew`, чтобы выделить память для массива. Во втором примере объявляется локальный массив.  
  
```  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *квалификаторы* [необязательно]  
 Один или несколько следующих спецификаторов класса хранения: [изменяемый](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [статический](../cpp/static-members-cpp.md).  
  
 `array-type`  
 Тип переменной массива. Допустимые типы: класса среды выполнения Windows и базовые типы, классы и структуры, классы и структуры значений, собственные указатели (`type*`) и собственные типы POD (обычные старые данные).  
  
 `rank` [необязательный параметр]  
 Число измерений массива. Значение по умолчанию — 1; максимальное число — 32. Каждое измерение массива само является массивом.  
  
 `identifier`  
 Имя переменной массива.  
  
 `initialization-type`  
 Тип значений, которые инициализируют массив. Как правило, `array-type` и `initialization-type` относятся к одному и тому же типу. Однако при наличии преобразования из `initialization-type` в `array-type` (например, если `initialization-type` является производным от `array-type`) типы могут быть разными.  
  
 `rank-size-list`  
 Разделенный запятыми список размеров каждого измерения массива. Если задан параметр `initialization-list`, компилятор может определить размер каждого измерения, и параметр `rank-size-list` можно опустить. 
  
 `initialization-list` [необязательный параметр]  
 Разделенный запятыми список инициализирующих элементы массива значений в фигурных скобках. Вложенная разделенный запятыми список *список инициализации* элементы, которые инициализируют элементы в многомерный массив.  
  
 Например если `rank-size-list` были `(3)`, который объявляет одномерный массив из 3 элементов `initialization list` может быть `{1,2,3}`. Если `rank-size-list` были `(3,2,4)`, который объявляет трехмерный массив из 3 элементов первого измерения, два элемента во втором и четыре элемента в третьем, `initialization-list` может быть `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>Примечания  
  
 `array` в [платформы, по умолчанию и пространства имен cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) пространства имен.  
  
 Как и в стандартной версии C++, индексы массива начинаются от нуля, и массив индексируется с помощью квадратных скобок ([]). В отличие от стандартной версии C++, индексы многомерного массива указываются в списке индексов каждого измерения вместо набора операторов квадратных скобок ([]) для каждого измерения. Например *идентификатор*[*index1*, *index2*] вместо *идентификатор*[*index1*] [ *index2*].  
  
 Все управляемые массивы являются производными от `System::Array`. Любой метод или свойство `System::Array` может применяться непосредственно к переменной массива.  
  
 При создании массива указателей на управляемый класс элементы массива инициализируются нулем.  
  
 При создании массива, тип элементов которого является типом значения `V`, к каждому элементу массива применяется конструктор по умолчанию для `V`. Дополнительные сведения см. в разделе [эквиваленты C++ собственных типов .NET Framework (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Во время компиляции, можно обнаружить, является ли тип общих массива среды выполнения (CLR) языка с `__is_ref_array(type)`. Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 В следующем примере создается одномерный массив из 100 элементов и трехмерный массив с 3 элементами в первом измерении, 5 элементами во втором и 6 элементами в третьем.  
  
```cpp  
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
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)