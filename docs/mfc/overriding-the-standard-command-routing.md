---
title: "Переопределение стандартной маршрутизации команд | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a8f926a2aa9ed48dac24f75850876bbd1e04ef4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-the-standard-command-routing"></a>Переопределение стандартной маршрутизации команд
В редких случаях при необходимо реализовать вариации Стандартная framework маршрутизации можно переопределить его. Необходимо изменить маршрутизацию в один или несколько классов, переопределив `OnCmdMsg` в этих классах. Сделать это:  
  
-   В классе, который нарушает порядок, чтобы передать объект не по умолчанию.  
  
-   В новый объект не по умолчанию или в целевые объекты команд его в свою очередь может передавать команды.  
  
 При вставке некоторых новый объект в маршрутизации, его класс должен быть классом целевой объект команды. В используемой версии переопределения `OnCmdMsg`, необходимо вызвать версию, которая переопределение. В разделе [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) функции-члена класса `CCmdTarget` в *Справочник по библиотеке MFC* и версии в классах, таких как `CView` и **CDocument** в Указанный исходный код для примера.  
  
## <a name="see-also"></a>См. также  
 [Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

