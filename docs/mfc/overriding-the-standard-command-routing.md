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
ms.openlocfilehash: 58156f6d1c361c24dc6cf04a9208157d614f91a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929014"
---
# <a name="overriding-the-standard-command-routing"></a>Переопределение стандартной маршрутизации команд
В редких случаях при необходимо реализовать вариации Стандартная framework маршрутизации можно переопределить его. Необходимо изменить маршрутизацию в один или несколько классов, переопределив `OnCmdMsg` в этих классах. Сделать это:  
  
-   В классе, который нарушает порядок, чтобы передать объект не по умолчанию.  
  
-   В новый объект не по умолчанию или в целевые объекты команд его в свою очередь может передавать команды.  
  
 При вставке некоторых новый объект в маршрутизации, его класс должен быть классом целевой объект команды. В используемой версии переопределения `OnCmdMsg`, необходимо вызвать версию, которая переопределение. В разделе [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) функции-члена класса `CCmdTarget` в *Справочник по библиотеке MFC* и версии в классах, таких как `CView` и `CDocument` в предоставленных исходного кода, примеры.  
  
## <a name="see-also"></a>См. также  
 [Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

