---
title: "Сообщения об ошибках ML | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09478bd3cff63e890014c6c14b11335feb8dfb3f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ml-error-messages"></a>Сообщения об ошибках ML
Сообщения об ошибках, создаваемых компонентами MASM делятся на три категории:  
  
-   **Неустранимые ошибки.** Они указывают серьезная проблема, препятствующая завершению его обычный процесс служебную программу.  
  
-   **Некритичные ошибки.** Программа может завершить его. В этом случае результат не скорее всего, будут нужную ссылку.  
  
-   **Предупреждения.** Эти сообщения указывают условия, которые могут помешать получения нужных результатов.  
  
 Все сообщения об ошибках имеют следующий вид:  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 Здесь:  
  
 `Utility`  
 Программа, отправлено сообщение об ошибке.  
  
 *Filename*  
 Файл, содержащий условие, вызвавшую ошибку.  
  
 *Line*  
 Приблизительное строке, где существует условие ошибки.  
  
 *Error_type*  
 Неустранимая ошибка, ошибка или предупреждение.  
  
 *Код*  
 Код ошибки уникальный 5 или 6-цифр.  
  
 `Message_text`  
 Короткие общие Описание условия ошибки.  
  
## <a name="see-also"></a>См. также  
 [Справочные материалы по ассемблеру Microsoft Macro Assembler](../../assembler/masm/microsoft-macro-assembler-reference.md)