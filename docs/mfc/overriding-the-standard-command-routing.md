---
title: Переопределение стандартной маршрутизации команд | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13f6c8f262061477da95a4863965c04e9d75c49a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-the-standard-command-routing"></a>Переопределение стандартной маршрутизации команд
В редких случаях при необходимо реализовать вариации Стандартная framework маршрутизации можно переопределить его. Необходимо изменить маршрутизацию в один или несколько классов, переопределив `OnCmdMsg` в этих классах. Сделать это:  
  
-   В классе, который нарушает порядок, чтобы передать объект не по умолчанию.  
  
-   В новый объект не по умолчанию или в целевые объекты команд его в свою очередь может передавать команды.  
  
 При вставке некоторых новый объект в маршрутизации, его класс должен быть классом целевой объект команды. В используемой версии переопределения `OnCmdMsg`, необходимо вызвать версию, которая переопределение. В разделе [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) функции-члена класса `CCmdTarget` в *Справочник по библиотеке MFC* и версии в классах, таких как `CView` и **CDocument** в Указанный исходный код для примера.  
  
## <a name="see-also"></a>См. также  
 [Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

