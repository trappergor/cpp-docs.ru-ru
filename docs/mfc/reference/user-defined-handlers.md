---
title: Пользовательские обработчики
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.handlers
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: d7c735531e4e2bd4da37ef7ba89cc9c4f9222b47
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262016"
---
# <a name="user-defined-handlers"></a>Пользовательские обработчики

Прототипы функции соответствуют следующие записи карты.

|Запись сопоставления|Прототип функции|
|---------------|------------------------|
|ON_MESSAGE ( \<сообщения >, \<memberFxn >)|memberFxn LRESULT afx_msg (WPARAM, LPARAM);|
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >, \<memberFxn >)|memberFxn LRESULT afx_msg (WPARAM, LPARAM);|
|ON_THREAD_MESSAGE ( \<сообщения >, \<memberFxn >)|void memberFxn afx_msg (WPARAM, LPARAM);|
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >, \<memberFxn >)|void memberFxn afx_msg (WPARAM, LPARAM);|

## <a name="see-also"></a>См. также

[Схемы сообщений](../../mfc/reference/message-maps-mfc.md)<br/>
[Обработчики для сообщений WM_](../../mfc/reference/handlers-for-wm-messages.md)
