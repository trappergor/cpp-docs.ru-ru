---
title: "Как: использование перекрестной ссылки схемы сообщений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.messages
dev_langs: C++
helpviewer_keywords: windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ffa7b39962d78476e971750e92569eb14229606b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Практическое руководство. Использование перекрестной ссылки схемы сообщений
В операциях с меткой \<memberFxn >, написать собственные функции-члена для производного [CWnd](../../mfc/reference/cwnd-class.md) класса. Присвойте функции любое имя по своему выбору. Остальные функции, такие как `OnActivate`, функции-члены класса являются `CWnd`. При вызове, передаваемого сообщения `DefWindowProc` функции Windows. Для обработки сообщений уведомлений Windows, переопределите соответствующий `CWnd` функция в производном классе. Функции следует вызвать переопределенной функции базового класса для базового класса и отреагировать на сообщение Windows.  
  
 Во всех случаях поместите прототип функции в `CWnd`-заголовок производного класса, а код элемент карты сообщений, как показано.  
  
 Используются следующие термины:  
  
|Термин|Определение|  
|----------|----------------|  
|id|Все определяемые пользователем идентификатор элемента меню (**WM_COMMAND** сообщения) или идентификатор (сообщения уведомления дочерних окон) элемента управления.|  
|«сообщение» и «wNotifyCode»|Windows сообщений идентификаторы, как определено в WINDOWS. З.|  
|nMessageVariable|Имя переменной, которая содержит возвращаемое значение **RegisterWindowMessage** функции Windows.|  
  
## <a name="see-also"></a>См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)

