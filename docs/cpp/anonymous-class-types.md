---
title: "Типы анонимных классов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы анонимных классов"
  - "типы классов, анонимные"
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Типы анонимных классов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Классы могут быть анонимными, т. е. их можно объявить без *идентификатора*.  Это полезно при замене имени класса именем `typedef`, как показано в следующем примере.  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
> [!NOTE]
>  Использование анонимных классов, показанное в предыдущем примере, полезно для поддержки совместимости с существующими кодом C.  В некотором коде C широко распространено использование `typedef` вместе с анонимными структурами.  
  
 Анонимные классы также полезны, если требуется, чтобы ссылка на член класса отображалась так, как если бы она не содержалась в отдельном классе, как показано в следующем примере.  
  
```  
struct PTValue  
{  
    POINT ptLoc;  
    union  
    {  
        int  iValue;  
        long lValue;  
    };  
};  
  
PTValue ptv;  
```  
  
 В предыдущем примере доступ к `iValue` можно получить с помощью оператора выбора члена объекта \(**.**\) следующим образом.  
  
```  
int i = ptv.iValue;  
```  
  
 Анонимные классы имеют некоторые ограничения.  \(Дополнительные сведения об анонимных объединениях см. в разделе [Объединения](../cpp/unions.md).\) Анонимные классы:  
  
-   Не могут иметь конструктор или деструктор.  
  
-   Не могут быть переданы в качестве аргументов в функции \(если проверка типов не отменена с помощью многоточия\).  
  
-   Не могут быть возвращены в качестве возвращаемых значений из функций.  
  
## Анонимные структуры  
  
### Блок, относящийся только к системам Microsoft  
 Расширение Microsoft C позволяет объявить переменную структуры в другой структуре без указания ее имени.  Эти вложенные структуры называются анонимными структурами.  В C\+\+ анонимные структуры не допускаются.  
  
 Можно получить доступ к членам анонимной структуры, как если бы они были членами содержащей их структуры.  
  
```  
// anonymous_structures.c  
#include <stdio.h>  
  
struct phone  
{  
    int  areacode;  
    long number;  
};  
  
struct person  
{  
    char   name[30];  
    char   gender;  
    int    age;  
    int    weight;  
    struct phone;    // Anonymous structure; no name needed  
} Jim;  
  
int main()  
{  
    Jim.number = 1234567;  
    printf_s("%d\n", Jim.number);     
}  
//Output: 1234567  
```  
  
### Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [\(NOTINBUILD\) Defining Class Types](http://msdn.microsoft.com/ru-ru/e8c65425-0f3a-4dca-afc2-418c3b1e57da)