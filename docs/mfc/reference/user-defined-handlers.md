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
ms.openlocfilehash: 4d2102668b7cc964e6fe3bffdcc6931a2961a737
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562257"
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

