---
title: "Вставки токена (##) оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '##'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b2f77a2bd61080c398256c5d9c28085ec779d2e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="token-pasting-operator-"></a>Оператор вставки токена (##)
Оператор двойной решетки или «вставки токена» (**##**), который иногда называется «объединение» оператора используется в макросах, подобных объектов и функций. Он позволяет объединить отдельные токены в один и поэтому не может быть первым или последним токеном в определении макроса.  
  
 Если перед формальным параметром в определении макроса или после него находится оператор вставки токена, этот формальный параметр сразу же заменяется неразвернутым фактическим аргументом. До замены расширение макроса в аргументе не выполняется.  
  
 Затем все вхождения оператора вставки токена в *строке токена* удаляется, и токены, предшествующие и следующие за ним объединяются. Результирующий токен должен быть допустимым. Если это так, токен сканируется для возможной замены, если он представляет имя макроса. Идентификатор представляет имя, которое будут иметь объединенные токены в программе до замены. Каждый токен представляет токен, определенный в программе или в командной строке компилятора. Пробел перед или после оператора необязателен.  
  
 В приведенном ниже примере показано использование оператора создания строки и оператора вставки токена для задания выходных данных программы.  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 Если макрос вызывается с числовым аргументом, например  
  
```  
paster( 9 );  
```  
  
 он создает инструкцию  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 которая становится инструкцией  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## <a name="example"></a>Пример  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы препроцессора](../preprocessor/preprocessor-operators.md)