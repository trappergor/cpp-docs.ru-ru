---
title: "Ошибка средств компоновщика LNK1179 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1179"
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка средств компоновщика LNK1179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый или поврежденный файл: дубликат "имени файла" COMDAT  
  
 Модуль объекта содержит два или более файла COMDAT с одинаковым именем.  
  
 Данная ошибка может возникать в результате использования параметра [\/H](../../build/reference/h-restrict-length-of-external-names.md), который ограничивает длину внешних имен, а также параметра [\/Gy](../../build/reference/gy-enable-function-level-linking.md), который выполняет упаковку функций в файлы COMDAT.  
  
## Пример  
 В следующем коде в `function1` и `function2` первые восемь символов идентичны.  При компиляции с параметрами **\/Gy** и **\/H8** возникает ошибка компоновки.  
  
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