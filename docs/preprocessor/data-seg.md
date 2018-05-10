---
title: data_seg | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
dev_langs:
- C++
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a463d966c681557525bb9512762731c01a7ce30
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="dataseg"></a>data_seg
Задает сегмент данных, в котором инициализированные переменные сохраняются в OBJ-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Примечания  
 Значение этих терминов *сегмент* и *раздел* являются взаимозаменяемыми в этом разделе.  
  
 OBJ-файлы можно просматривать с [dumpbin](../build/reference/dumpbin-command-line.md) приложения. По умолчанию сегмент в OBJ-файле для инициализированных переменных — DATA. Неинициализированные переменные считаются инициализированными с нулем и сохраняются в BSS-файле.  
  
 **data_seg** без параметров сбрасывает сегмент до Data.  
  
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
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Данные, предоставленные с помощью **data_seg** не сохраняют никакой информации о своем расположении.  
  
 В разделе [/SECTION](../build/reference/section-specify-section-attributes.md) список имен не следует использовать при создании раздела.  
  
 Можно также задать разделы для переменных const ([const_seg](../preprocessor/const-seg.md)), неинициализированных данных ([bss_seg](../preprocessor/bss-seg.md)) и функции ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)