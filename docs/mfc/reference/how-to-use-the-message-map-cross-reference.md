---
title: 'Практическое: использование перекрестной ссылки схемы сообщений | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fccdf620cbdaeffc7fb201e014edc4c7c1dddc83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434457"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Практическое руководство. Использование перекрестной ссылки схемы сообщений

В операциях с меткой \<memberFxn >, написать собственную функцию члена для производного [CWnd](../../mfc/reference/cwnd-class.md) класса. Присвойте любое имя, но следует функции. Остальные функции, такие как `OnActivate`, являются функциями-членами класса `CWnd`. При вызове, передаваемого сообщения `DefWindowProc` функции Windows. Для обработки сообщений уведомлений Windows, переопределите соответствующие `CWnd` функция в производном классе. Функции следует вызвать переопределенной функции базового класса для базового класса и Windows отвечает на сообщение.

Во всех случаях поместите прототип функции в `CWnd`-заголовок в производном классе и код элемент карты сообщений, как показано.

Используются следующие термины:

|Термин|Определение|
|----------|----------------|
|id|Идентификатор элемента меню, определяемые пользователем (WM_COMMAND-сообщения) или идентификатор элемента управления (сообщения уведомления дочерних окон).|
|«сообщение» и «wNotifyCode»|Windows сообщения идентификаторы, как определено в WINDOWS. З.|
|nMessageVariable|Имя переменной, которая содержит значение, возвращаемое `RegisterWindowMessage` функции Windows.|

## <a name="see-also"></a>См. также

[Схемы сообщений](../../mfc/reference/message-maps-mfc.md)

