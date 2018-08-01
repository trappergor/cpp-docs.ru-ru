---
title: Значение NULL, оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab391bb75dd6e7a2ef1ccf0951fa93770e6cd316
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408779"
---
# <a name="null-statement"></a>Оператор NULL
«Оператор null» — это инструкция выражения с *выражение* отсутствует. Она полезна, если синтаксис языка требует инструкции, но не оценки выражения. Она состоит из точки с запятой.  
  
 Инструкции null часто используются как местозаполнители в инструкциях итерации или как инструкции, в которых нужно разместить метки в конце сложных инструкций или функций.  
  
 В следующем фрагменте кода показано, как копировать одну строку в другую. Кроме того, код содержит инструкцию null.  
  
```cpp 
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Оператор выражений](../cpp/expression-statement.md)