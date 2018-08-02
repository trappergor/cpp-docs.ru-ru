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
ms.openlocfilehash: 8775f752a541d2a250e9c1c5a0c325b684335988
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464604"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений
Главное ограничение на использование обработчиков исключений в коде в том, что нельзя использовать **goto** инструкцию, чтобы перейти к **__try** блока инструкций. Входить в этот блок необходимо только через обычный поток управления. Вы можете переходить из **__try** инструкции блокировать и создавать вложенные обработчики исключений, как захотите.  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)