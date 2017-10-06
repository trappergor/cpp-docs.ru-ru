---
title: "оператор __alignof | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs:
- C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 66ec7ff196a4f22aec043d8b76faf0189e05cd0f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="alignof-operator"></a>Оператор __alignof
В C++ 11 имеется оператор `alignof`, возвращающий выравнивание (в байтах) заданного типа. Для обеспечения максимальной переносимости кода следует использовать оператор alignof вместо оператора __alignof, тесно связанного с системами Майкрософт.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Возвращает значение типа **size_t** , является требованием к выравниванию типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      __alignof(   
   type    
)  
```  
  
## <a name="remarks"></a>Примечания  
 Пример:  
  
|Выражение|Значение|  
|----------------|-----------|  
|**__alignof (char)**|1|  
|**__alignof (краткое).**|2|  
|**__alignof (int)**|4|  
|**__alignof ( \__int64)**|8|  
|**__alignof (float)**|4|  
|**__alignof (double)**|8|  
|**__alignof (char\* )**|4|  
  
 Значение `__alignof` совпадает со значением `sizeof` для базовых типов. Однако рассмотрим следующий пример.  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 В этом случае значение `__alignof` является требованием к выравниванию наибольшего элемента в структуре.  
  
 Аналогичным образов, в  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)` равно `32`.  
  
 Одним из применений выражения `__alignof` является его использование в качестве параметра одной из пользовательских подпрограмм выделения памяти. Например, в следующей определенной структуре `S` можно вызвать подпрограмму выделения памяти с именем `aligned_malloc` для выделения памяти на определенной границе выравнивания.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Дополнительные сведения об изменении выравнивания см. в следующих разделах.  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md) (x64 64)  
  
 Дополнительные сведения о различиях в выравнивании в коде для 32- (x86) и 64-разрядных (x64) сред см. в статье  
  
-   [Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
