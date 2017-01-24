---
title: "Правила и ограничения dllimport/dllexport | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "dllexport - атрибут [C++]"
  - "dllexport - атрибут [C++], ограничения и правила"
  - "атрибут DllImport [C++], ограничения и правила"
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Правила и ограничения dllimport/dllexport
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
-   Если функция объявлена без атрибута **dllimport** или `dllexport`, то она не считается частью интерфейса DLL.  Поэтому определение функции должно находиться в том же самом модуле или в другом модуле той же программы.  Для того чтобы включить функцию в интерфейс DLL, необходимо в другом модуле объявить определение функции, указав для нее атрибут `dllexport`.  В противном случае при сборке клиента возникнет ошибка компоновщика.  
  
-   Если в одном и том же модуле содержатся объявления одной и той же функции с атрибутами **dllimport** и `dllexport`, то атрибут `dllexport` имеет приоритет перед **dllimport**.  Однако компилятор создает предупреждение.  Например:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllExport void func1( void );   /* Warning; dllexport */  
                                       /* takes precedence. */  
  
    ```  
  
-   Вы не можете инициализировать указатель на статические данные с адресом объекта данных, объявленного с атрибутом **dllimport**.  Например, следующий код вызывает ошибки:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport int i;  
       .  
       .  
       .  
       int *pi = &i;                           /* Error */  
  
       void func2()  
       {  
          static int *pi = &i;                   /* Error */  
       }  
  
    ```  
  
-   Если инициализировать указатель на статическую функцию с адресом функции, объявленной с атрибутом **dllimport**, то указатель будет установлен не на адрес функции, а на адрес преобразователя импорта DLL \(заглушки, которая передает управление функции\).  Следующее присваивание не порождает сообщения об ошибке:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void   
       .  
       .  
       .  
       static void ( *pf )( void ) = &func1;   /* No Error */  
  
       void func2()  
       {  
          static void ( *pf )( void ) = &func1;  /* No Error */  
       }  
  
    ```  
  
-   Поскольку программа с атрибутом `dllexport` в объявлении объекта должна содержать определение этого объекта, то указатель на глобальную или локальную статическую функцию можно инициализировать с адресом функции с атрибутом `dllexport`.  Аналогичным образом указатель на глобальные или локальные статические данные можно инициализировать с адресом объекта данных с атрибутом `dllexport`.  Например:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllImport int i;  
  
       DllExport void func1( void );  
       DllExport int i;  
       .  
       .  
       .  
       int *pi = &i;                            /* Okay */  
       static void ( *pf )( void ) = &func1;    /* Okay */  
  
       void func2()  
       {  
          static int *pi = i;                     /* Okay */  
          static void ( *pf )( void ) = &func1;   /* Okay */  
       }  
  
    ```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Функции импорта и экспорта DLL](../Topic/DLL%20Import%20and%20Export%20Functions.md)