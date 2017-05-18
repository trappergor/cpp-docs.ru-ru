---
title: "Ввод и вывод | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 9
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 424cf158f8d5801f0fd4e1b92e9c95d792832b2d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="input-and-output"></a>Ввод и вывод
Функции ввода-вывода производят чтение из файлов и устройств и запись в них. Операции файлового ввода-вывода выполняются в текстовом или двоичном режиме. Библиотека времени выполнения Microsoft содержит три типа функций ввода-вывода:  
  
-   Функции [потокового ввода-вывода](../c-runtime-library/stream-i-o.md) обрабатывают данные как поток отдельных символов.  
  
-   Функции [низкоуровневого ввода-вывода](../c-runtime-library/low-level-i-o.md) напрямую вызывают операционную систему для выполнения операций более низкого уровня, чем поддерживаемые при потоковом вводе-выводе.  
  
-   Функции [ввода-вывода на консоль и в порты](../c-runtime-library/console-and-port-i-o.md) производят чтение или запись непосредственно на консоль (клавиатуру и экран) или в порт ввода-вывода (например, порт принтера).  
  
    > [!NOTE]
    >  Поскольку потоковые функции используют буфер, а низкоуровневые функции буфер не используют, эти два типа функций обычно несовместимы. Для обработки конкретного файла используйте либо только потоковые, либо только низкоуровневые функции.  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
