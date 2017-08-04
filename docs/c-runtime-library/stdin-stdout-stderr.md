---
title: "Потоки stdin, stdout, stderr | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 331b60a8cd06e42c032c6d8c81b58b8e4f4501ae
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr
## <a name="syntax"></a>Синтаксис  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Это стандартные потоки для ввода, вывода и вывода ошибок.  
  
 По умолчанию стандартный ввод — чтение с клавиатуры, в то время как стандартный вывод и стандартный вывод ошибок печатаются на экране.  
  
 Следующие указатели потока доступны для получения стандартных потоков:  
  
|Указатель|Поток|  
|-------------|------------|  
|`stdin`|Стандартный ввод|  
|**stdout**|Стандартный вывод|  
|`stderr`|Стандартная ошибка|  
  
 Эти указатели можно использовать в качестве аргументов для функций. Некоторые функции, например **getchar** и `putchar`, используют `stdin` и **stdout** автоматически.  
  
 Эти указатели являются константами, и им не могут быть присвоены новые значения. Функцию `freopen` можно использовать, чтобы перенаправить потоки в файлы на диске или на другие устройства. Операционная система позволяет перенаправлять стандартный ввод и вывод программы на командном уровне.  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../c-runtime-library/stream-i-o.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)
