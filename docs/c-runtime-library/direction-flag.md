---
title: "Флаг направления | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: b26cb08800bf7d2855c7972c63c0bea414d58c99
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="direction-flag"></a>Флаг направления
Флаг направления — это флаг ЦП, относящийся к процессорам Intel 80x86. Он применяется для всех инструкций сборки, которые используют префикс REP (повтор), например для MOVS, MOVSD, MOVSW и др. Если флаг направления не установлен, предоставляемые этим инструкциям адреса увеличиваются.  
  
 Подпрограммы времени выполнения C предполагают, что флаг направления не установлен. Если вы используете другие функции совместно с функциями времени выполнения C, эти дополнительные функции должны не изменять флаг направления или восстанавливать его исходное состояние. Если предполагать, что флаг направления при входе не установлен, код времени выполнения будет более быстрым и эффективным.  
  
 Функции библиотеки времени выполнения C, например подпрограммы обработки строк и управления буфером, ожидают, что флаг направления не установлен.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)
