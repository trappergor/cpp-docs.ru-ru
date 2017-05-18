---
title: "Неполные типы | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 89de19cb4a6fceca93a2ca3ec8ced10aaaf2c31f
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="incomplete-types"></a>Неполные типы
Неполный тип — это тип, который описывает идентификатор, но не содержит информации, необходимой для определения размера идентификатора. Неполным типом может быть:  
  
-   Тип структуры, для которой еще не были определены члены.  
  
-   Тип объединения для которого еще не были определены члены.  
  
-   Тип массива, для которого еще не были определены размерности.  
  
 Тип void является неполным типом, который невозможно сделать полным. Чтобы дополнить неполный тип, укажите отсутствующие данные. В следующих примерах показано, как создать и дополнить неполные типы.  
  
-   Чтобы создать неполный тип структуры, объявите тип структуры, не указывая ее члены. В этом примере указатель `ps` указывает на неполный тип структуры с именем `student`.  
  
    ```  
    struct student *ps;  
    ```  
  
-   Чтобы дополнить неполный тип структуры, объявите тот же самый тип структуры ниже в той же самой области видимости и задайте его члены, как в следующем примере:  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   Чтобы создать неполный тип массива, объявите тип массива, не указывая для него число повторений. Например:  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   Чтобы дополнить неполный тип массива, объявите то же самое имя ниже в той же самой области видимости и задайте его число повторений, как в следующем примере:  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>См. также  
 [Объявления и типы](../c-language/declarations-and-types.md)
