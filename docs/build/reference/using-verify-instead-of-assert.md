---
title: "Использование VERIFY вместо ASSERT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSERT - операторы"
  - "утверждения, отладка"
  - "утверждения, операторы ASSERT - устранение неполадок"
  - "отладка [MFC], ASSERT - операторы"
  - "отладка утверждений"
  - "VERIFY - макрос"
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Использование VERIFY вместо ASSERT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возможно, при запуске версии отладчика для приложения MFC проблем не возникнет.  Тем не менее в работе версии выпуска того же приложения возникают сбои, приложение возвращает неправильные результаты и не функционирует нормально.  
  
 Данная проблема может возникнуть в результате помещения важного участка кода в оператор ASSERT, чтобы проверить, насколько корректно он работает.  Поскольку в построении выпуска программы MFC операторы ASSERT преобразованы в комментарии, код в построении выпуска работать не будет.  
  
 Если операторы ASSERT используются для проверки выполнения вызова функции, рекомендуется вместо них использовать макрос [VERIFY](../Topic/VERIFY.md).  Макрос VERIFY оценивает собственные аргументы как в сборке выпуска, так и в отладочном построении приложения.  
  
 Также рекомендуется присвоить временной переменной возвращаемое значение функции, а затем проверить переменную в операторе ASSERT.  
  
 Рассмотрим следующий фрагмент кода:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Данный код корректно работает в отладочной версии приложения MFC.  Если не удается выполнить вызов `calloc( )`, выводится сообщение о диагностике, содержащее информацию о файле и номере строки.  Тем не менее в коммерческой сборке приложения MFC:  
  
-   никогда не выполняется вызов `calloc( )`, вследствие чего `buf` остается неинициализированным, или  
  
-   `strcpy_s( )` выполняет копирование "`Hello, World`" в произвольный участок памяти, вследствие чего либо происходит сбой в приложении, либо система перестает отвечать, либо  
  
-   `free()` пытается высвободить память, которая не была выделена.  
  
 Для корректного использования операторов ASSERT образец кода необходимо изменить следующим образом:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Или можно использовать вместо него макрос VERIFY:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## См. также  
 [Устранение проблем построения выпуска](../../build/reference/fixing-release-build-problems.md)