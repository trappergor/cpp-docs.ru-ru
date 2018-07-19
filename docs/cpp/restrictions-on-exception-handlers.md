---
title: Ограничения обработчиков исключений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13971ede3aef6d223b1c631c4a28f8bf190e7174
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37938787"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений
Главное ограничение на использование обработчиков исключений в коде в том, что нельзя использовать **goto** инструкцию, чтобы перейти к **__try** блока инструкций. Входить в этот блок необходимо только через обычный поток управления. Вы можете переходить из **__try** инструкции блокировать и создавать вложенные обработчики исключений, как захотите.  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)