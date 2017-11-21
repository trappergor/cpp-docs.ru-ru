---
title: "1.1 область | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b4f348f55cb956802bab9651b22804c941c53cdb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="11-scope"></a>1.1 Область
Эта спецификация охватывает параллелизация только управляемое пользователем, при котором пользователь явно указывает действия, выполняемые в компиляторе и системе времени выполнения для параллельного выполнения программы. Реализации OpenMP C и C++ не требуется проверять зависимости, конфликтов, взаимоблокировки, состояние гонки или других проблем, которые приводят к некорректной программы выполнения. Пользователь несет ответственность за обеспечение правильности выполнения приложения с помощью конструкции OpenMP C и C++ API. Созданный компилятором автоматическую параллелизацию и директивы компилятора для помощи такой параллелизации не рассматривается в этом документе.