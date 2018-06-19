---
title: Ошибка средств компоновщика LNK1179 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72a531397c3c101fbff937f293f772c5f6778523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300219"
---
# <a name="linker-tools-error-lnk1179"></a>Ошибка средств компоновщика LNK1179
Недопустимый или поврежденный файл: повторяющийся COMDAT «имя_файла»  
  
 Модуль объекта содержит два или более записи COMDAT с тем же именем.  
  
 Эта ошибка может вызываться с помощью [/H](../../build/reference/h-restrict-length-of-external-names.md), который ограничивает длину внешних имен, и [/Gy](../../build/reference/gy-enable-function-level-linking.md), пакеты, функций COMDAT.  
  
## <a name="example"></a>Пример  
 В следующем коде `function1` и `function2` идентичных первые восемь символов. Компиляция с **/Gy** и **/H8** возникает ошибка компоновки.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```