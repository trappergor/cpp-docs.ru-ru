---
title: Сигналы по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- default signals
- defaults, signals
ms.assetid: db9fc17b-75c0-4d33-86be-c536584bbede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78c369665d398d4b326cf8d27ad0944a594fe1a4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758941"
---
# <a name="default-signals"></a>Сигналы по умолчанию

**ANSI 4.7.1.1** Если до вызова обработчика сигнала не выполняется эквивалент `signal(sig, SIG_DFL)`, сигнал блокируется.

В начале выполнения программы для сигналов задаются состояния по умолчанию.  
  
## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)