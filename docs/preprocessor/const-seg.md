---
title: "const_seg | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bcd84415737ee5fb8584f04b56c1df895145a3b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="constseg"></a>const_seg
Указывает сегмент где [const](../cpp/const-cpp.md) переменные сохраняются в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Примечания  
 Значение этих терминов *сегмент* и *раздел* являются взаимозаменяемыми в этом разделе.  
  
 OBJ-файлы можно просматривать с [dumpbin](../build/reference/dumpbin-command-line.md) приложения. По умолчанию для хранения переменных `const` в OBJ-файле используется сегмент .rdata. Некоторые переменные `const`, например скаляры, автоматически подставляются в поток кода. Подставляемый код не отображается в сегменте .rdata.  
  
 Определение объекта, требующее динамической инициализации в `const_seg`, приводит к неопределенному поведению.  
  
 `#pragma const_seg` без параметров сбрасывает сегмент до .rdata.  
  
 `push` (необязательно)  
 Помещает запись во внутренний стек компилятора. `push` может иметь `identifier` и `segment-name`.  
  
 `pop` (необязательно)  
 Удаляет запись из вершины внутреннего стека компилятора.  
  
 `identifier` (необязательно)  
 При использовании с директивой `push` присваивает имя записи во внутреннем стеке компилятора. При использовании с директивой `pop` записи из внутреннего стека извлекаются до тех пор, пока не будет удален идентификатор `identifier`; если идентификатор `identifier` во внутреннем стеке не найден, ничего не извлекается.  
  
 `identifier` позволяет с помощью одной команды `pop` вывести сразу несколько записей.  
  
 "`segment-name`" (необязательно)  
 Имя сегмента. При использовании с `pop` стек выводится, а `segment-name` становится активным именем сегмента.  
  
 "`segment-class`" (необязательно)  
 Включено для обеспечения совместимости с C++ до версии 2.0. Игнорируется.  
  
## <a name="example"></a>Пример  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
```Output  
test1  
test2  
test3  
test4  
```  
  
## <a name="comments"></a>Комментарии  
 В разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.  
  
 Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), неинициализированных данных ([bss_seg](../preprocessor/bss-seg.md)) и функции ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)