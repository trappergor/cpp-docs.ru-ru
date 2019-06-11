---
title: Пользовательские обработчики
ms.date: 11/04/2016
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: f39440d333e968c236ae5ccd750cec8854cb0530
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611547"
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
