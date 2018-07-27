---
title: Описатель класса хранения extern | Документация Майкрософт
ms.custom: ''
ms.date: 07/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365f4cf424ee51c493859e1d79f733b2cfcf331c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964188"
---
# <a name="extern-storage-class-specifier"></a>Спецификатор класса хранения extern

Переменная, объявленная с использованием описателя для класса хранения **extern**, представляет собой ссылку на переменную с тем же именем, определенную в другом исходном файле. Она используется, чтобы сделать видимым определение переменной внешнего уровня. Для переменной, объявленной как **extern**, не выделено хранилище; по сути, это только имя. 
  
## <a name="example"></a>Пример  
 Этот пример иллюстрирует объявления на внутреннем и внешнем уровнях.  
  
```c  

// Source1.c  

int i = 1;


// Source2. c

#include <stdio.h>  

// Refers to the i that is defined in Source1.c:   
extern int i;

void func(void);

int main()
{
    // Prints 1:   
    printf_s("%d\n", i);
    func();
    return;
}

void func(void)
{
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;

    // This definition of i hides the global i in Source.c:   
    int i = 16;

    // Prints 16, 1:  
    printf_s("%d\n%d\n", i, *external_i);
}
```  
  
 В этом примере переменная `i` определяется в Source1.c с исходным значением 1. Объявление **extern** в Source2.c делает переменную i видимой в этом файле. 

 В функции `func` адрес глобальной переменной `i` используется для инициализации переменной указателя `external_i` с описателем **static**. Это возможно, поскольку глобальная переменная имеет **статическое** время существования, то есть ее адрес не меняется во время исполнения программы. Кроме того, переменная `i` определяется в пределах области `func` как локальная переменная с исходным значением 16. Это определение не влияет на значение переменной `i` внешнего уровня, которое скрыто благодаря использованию соответствующего имени для локальной переменной. Значение глобальной переменной `i` теперь доступно только через указатель `external_i`.   
  
## <a name="see-also"></a>См. также  
 [Спецификаторы классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md)