---
title: "__unaligned | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
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
ms.openlocfilehash: 9f899add9a1306344a10840220f3b7504e917d91
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="unaligned"></a>__unaligned
При объявлении указателя с модификатором `__unaligned` компилятор предполагает, что указатель обращается к данным без выравнивания. Поэтому для тех приложений, которые предназначены для компьютеров с процессором семейства Itanium, компилятор создает код, считывающий такие данные по одному байту за раз.  
  
## <a name="remarks"></a>Примечания  
 `__unaligned` Модификатор является допустимым для [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] и [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] компиляторы, но действует только для приложений, предназначенных для семейства Itanium. Этот модификатор описывает только выравнивание данных, к которым выполняется обращение. Сам по себе указатель считается выровненным.  
  
 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] Процессора создает ошибку выравнивания, когда он получает доступ к данным с неверным выравниванием и времени для обработки ошибки ослабляется производительности. Используйте модификатор `__unaligned`, чтобы указать процессору считывать по одному байту за раз и предотвратить ошибку. Этот модификатор не является обязательным для [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] приложений из-за [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] процессор обрабатывает данные с неверным выравниванием без ошибок.  
  
 Дополнительные сведения о выравнивании см. в разделах:  
  
-   [align](../cpp/align-cpp.md)  
  
-   [Оператор __alignof](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md)  
  
## <a name="example"></a>Пример  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)
