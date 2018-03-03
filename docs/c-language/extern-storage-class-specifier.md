---
title: "Описатель класса хранения extern | Документация Майкрософт"
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
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 448a659afaf7a0251d500da3d9878d30550b9180
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="extern-storage-class-specifier"></a>Спецификатор класса хранения extern
Переменная, объявленная с описателем класса хранения `extern`, представляет собой ссылку на переменную с тем же именем, определенным на внешнем уровне в любом из файлов исходного кода программы. Внутреннее объявление `extern` используется, чтобы сделать определение переменной внешнего уровня видимым в блоке. Если иное не объявлено на внешнем уровне, переменная, объявленная с использованием ключевого слова `extern`, видна только в блоке, в котором она объявлена.  
  
## <a name="example"></a>Пример  
 Этот пример иллюстрирует объявления на внутреннем и внешнем уровнях.  
  
```  
// extern_StorageClassSpecified.c  
#include <stdio.h>  
  
void other( void );  
  
int main()  
{  
    // Reference to i, defined below:   
    extern int i;  
  
    // Initial value is zero; a is visible only within main:   
    static int a;  
  
    // b is stored in a register, if possible:   
    register int b = 0;  
  
    // Default storage class is auto:   
    int c = 0;  
  
    // Values printed are 1, 0, 0, 0:   
    printf_s( "%d\n%d\n%d\n%d\n", i, a, b, c );  
    other();  
    return;  
}  
  
int i = 1;  
  
void other( void )  
{  
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;  
  
    // i is redefined; global i no longer visible:   
    int i = 16;  
  
    // This a is visible only within the other function:   
    static int a = 2;  
  
    a += 2;  
    // Values printed are 16, 4, and 1:  
    printf_s( "%d\n%d\n%d\n", i, a, *external_i );  
}  
```  
  
 В этом примере переменная `i` определяется на внешнем уровне с исходным значением 1. Объявление `extern` в функции `main` используется для объявления ссылки на `i` внешнего уровня. Переменная `a` с описателем **static** по умолчанию инициализируется значением 0, поскольку инициализатор опущен. Вызов метода `printf` печатает значения 1, 0, 0 и 0.  
  
 В функции `other` адрес глобальной переменной `i` используется для инициализации переменной указателя `external_i` с описателем **static**. Это возможно, поскольку глобальная переменная имеет **статическое** время существования, то есть ее адрес не меняется во время исполнения программы. Кроме того, переменная `i` переопределяется как локальная переменная с исходным значением 16. Это переопределение не влияет на значение `i` внешнего уровня, который скрыт путем использования его имени для локальной переменной. Значение глобального `i` теперь доступно только косвенно в пределах блока, через указатель `external_i`. Попытка присвоить указателю адрес переменной `i` с описателем **auto** завершится неудачей, поскольку этот адрес может быть разным при каждом входе в блок. Переменная `a` объявляется как **статическая** и инициализируется значением 2. Данная `a` не конфликтует с `a` в `main`, поскольку **статические** переменные на внутреннем уровне видны только внутри блока, в котором они определены.  
  
 Переменная `a` увеличивается на 2, давая результат 4. Если функция `other` снова вызывается в той же программе, исходное значение `a` будет равно 4. Внутренние **статические** переменные сохраняют свои значения, когда программа выходит из блока, в котором они определены, и затем повторно входит в него.  
  
## <a name="see-also"></a>См. также  
 [Спецификаторы классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md)