---
title: "bss_seg | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0dd1e24127129ef833cfd4906085eabbf1e5c380
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bssseg"></a>bss_seg
Задает сегмент, в котором неинициализированные переменные сохраняются в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Примечания  
 OBJ-файлы можно просматривать с [dumpbin](../build/reference/dumpbin-command-line.md) приложения. По умолчанию сегмент в OBJ-файле для неинициализированных данных — BSS. В некоторых случаях использование **bss_seg** может ускорить время загрузки благодаря группировке неинициализированных данных в один раздел.  
  
 **bss_seg** без параметров сбрасывает сегмент до BSS.  
  
 **Принудительная**(необязательно)  
 Помещает запись во внутренний стек компилятора. Объект **принудительной** может иметь *идентификатор* и *имя сегмента*.  
  
 **POP** (необязательно)  
 Удаляет запись из вершины внутреннего стека компилятора.  
  
 *Идентификатор* (необязательно)  
 При использовании с **принудительной**, присваивает имя записи во внутреннем стеке компилятора. При использовании с **pop**, извлекает записи из внутреннего стека до *идентификатор* удаляется; Если *идентификатор* не найден во внутреннем стеке, ничего не извлекается.  
  
 *Идентификатор* включает несколько записей, извлекаемых с одним **pop** команды.  
  
 *«Имя сегмента»*(необязательно)  
 Имя сегмента. При использовании с **pop**, стек выводится и *имя сегмента* становится активным именем сегмента.  
  
 *«Класс сегмента»* (необязательно)  
 Включено для обеспечения совместимости с C++ до версии 2.0. Игнорируется.  
  
## <a name="example"></a>Пример  
  
```  
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), функций ([code_seg](../preprocessor/code-seg.md)) и переменных const ([const_seg](../preprocessor/const-seg.md)).  
  
 Данные, предоставленные с помощью **bss_seg** pragma не сохраняют никакой информации о своем расположении.  
  
 В разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)