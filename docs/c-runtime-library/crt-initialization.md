---
title: "Инициализация CRT | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инициализация CRT [C++]"
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Инициализация CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описывается, как CRT инициализирует глобальные состояния в машинном коде.  
  
 По умолчанию компоновщик включает библиотеку CRT, которая предоставляет собственный код запуска.  Этот код запуска инициализирует библиотеку CRT, вызывает глобальные инициализаторы и затем вызывает предоставленную пользователем функцию `main` для консольных приложений.  
  
## Инициализация глобального объекта  
 Рассмотрим следующий код.  
  
```  
int func(void)  
{  
    return 3;  
}  
  
int gi = func();  
  
int main()  
{  
    return gi;  
}  
```  
  
 В соответствии со стандартом C\/C\+\+, `func()` необходимо вызывать перед тем, как выполнится `main()`.  Но кто вызывает её?  
  
 Один из способов определить это, \- установить точку останова в `func()`, отладить приложение, и просмотреть стек.  Это возможно, поскольку исходный код CRT входит в состав Visual Studio.  
  
 При просмотре функции в стеке, можно увидеть, что CRT в цикле просматривает список указателей функций и вызывает каждый из них по мере того, как они встречаются.  Эти функции похожи либо на `func()`, либо на конструкторы для экземпляров класса.  
  
 CRT получает список указателей функции от компилятора Visual C\+\+.  Если компилятор обнаруживает глобальный инициализатор, он создает динамический инициализатор в разделе `.CRT$XCU` \(где `CRT` \- имя раздела, и `XCU` \- имя группы\).  Чтобы получить список этих динамических инициализаторов, выполните команду **dumpbin \/all main.obj**, а затем найдите раздел `.CRT$XCU` \(где main.cpp компилируется как файл C\+\+, не файл C\).  Он будет аналогичен следующему:  
  
```  
SECTION HEADER #6  
.CRT$XCU name  
       0 physical address  
       0 virtual address  
       4 size of raw data  
     1F2 file pointer to raw data (000001F2 to 000001F5)  
     1F6 file pointer to relocation table  
       0 file pointer to line numbers  
       1 number of relocations  
       0 number of line numbers  
40300040 flags  
         Initialized Data  
         4 byte align  
         Read Only  
  
RAW DATA #6  
  00000000: 00 00 00 00                                      ....  
  
RELOCATIONS #6  
                                                Symbol    Symbol  
 Offset    Type              Applied To         Index     Name  
 --------  ----------------  -----------------  --------  ------  
 00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))  
```  
  
 CRT определяет два указателя:  
  
-   `__xc_a` в `.CRT$XCA`  
  
-   `__xc_z` в `.CRT$XCZ`  
  
 Обе группы не имеют других указанный символов, за исключением `__xc_a` и `__xc_z`.  
  
 Теперь, когда компоновщик считывает разные группы `.CRT`, он объединяет их в одном разделе и упорядочивает их по алфавиту.  Это означает, что определяемые пользователем глобальные инициализаторы \(которые компилятор Visual C\+\+ помещает в `.CRT$XCU`\) всегда будут идти после `.CRT$XCA` и перед `.CRT$XCZ`.  
  
 Раздел будет выглядит следующим образом:  
  
```  
.CRT$XCA  
            __xc_a  
.CRT$XCU  
            Pointer to Global Initializer 1  
            Pointer to Global Initializer 2  
.CRT$XCZ  
            __xc_z  
```  
  
 Таким образом, библиотека CRT использует и `__xc_a`, и `__xc_z`, чтобы определить начало и конец списка глобальных инициализаторов из\-за способа, в котором они располагаются в памяти после загрузки образа.  
  
## См. также  
 [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)