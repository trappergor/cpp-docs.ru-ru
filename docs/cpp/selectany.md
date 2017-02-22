---
title: "selectany | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "selectany_cpp"
  - "selectany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], selectany"
  - "selectany __declspec - ключевое слово"
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# selectany
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Сообщает компилятору, что объявленный элемент глобальных данных \(переменная или объект\) является универсальным COMDAT \(упакованной функцией\).  
  
## Синтаксис  
  
```  
  
__declspec( selectany ) declarator  
```  
  
## Заметки  
 Во время компоновки, если отображается несколько определений COMDAT, компоновщик выбирает один из них и игнорирует остальные.  При выборе параметра компоновщика [\/OPT: REF](../build/reference/opt-optimizations.md) \(оптимизации\) произойдет исключение COMDAT для удаления всех элементов данных без ссылок во выходных данных компоновщика.  
  
 Конструкторы и назначение с помощью глобальной функции или статических методов в объявлении не создадут ссылку и не предотвратят исключение \/OPT:REF.  Побочные эффекты такого кода не должны быть зависимыми, если не существует других ссылок на данные.  
  
 Для динамически инициализированных глобальных объектов `selectany` также удалит код инициализации объекта без ссылки.  
  
 Обычно элемент глобальных данных можно инициализировать только один раз в проекте EXE или DLL.  `selectany` можно использовать при инициализации глобальных данных, определенных в заголовках, если одинаковый заголовок отображается в нескольких исходных файлах.  `selectany` доступен в обоих компиляторах: C и C\+\+.  
  
> [!NOTE]
>  `selectany` можно применить только к существующей инициализации элементов глобальных данных, видимых извне.  
  
## Пример  
 В следующем коде демонстрируется использование атрибута `selectany`.  
  
```  
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
  
## Пример  
 В этом примере кода показано, как использовать атрибут `selectany`, чтобы включить свертывание записей COMDAT при использовании параметра компоновщика [\/OPT:ICF](../build/reference/opt-optimizations.md).  Обратите внимание, что данные должны быть отмечены `selectany` и внесены в раздел **const** \(только для чтения\).  Раздел, доступный только для чтения, необходимо указать явно.  
  
```  
// selectany2.cpp  
// in the following lines, const marks the variables as read only  
__declspec(selectany) extern const int ix = 5;  
__declspec(selectany) extern const int jx = 5;  
int main() {  
   int ij;  
   ij = ix + jx;  
}  
```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)