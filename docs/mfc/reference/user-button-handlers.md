---
title: Обработчики пользовательских кнопок
ms.date: 11/04/2016
f1_keywords:
- ON_BN_HILITE
- ON_BN_DOUBLECLICKED
- ON_BN_CLICKED
- ON_BN_PAINT
- ON_BN_DISABLE
- ON_BN_UNHILITE
helpviewer_keywords:
- ON_BN_PAINT
- user buttons [MFC]
- ON_BN_DOUBLECLICKED [MFC]
- ON_BN_DISABLE [MFC]
- ON_BN_UNHILITE [MFC]
- ON_BN_HILITE [MFC]
- ON_BN_CLICKED [MFC]
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
ms.openlocfilehash: 55bf42d88cca805a8a75165e6fa868b9925d4d4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542380"
---
# <a name="user-button-handlers"></a>Обработчики пользовательских кнопок

Прототипы функции соответствуют следующие записи карты.

|Запись сопоставления|Прототип функции|
|---------------|------------------------|
|ON_BN_CLICKED ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_BN_DISABLE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_BN_DOUBLECLICKED ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_BN_HILITE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_BN_PAINT ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_BN_UNHILITE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|

## <a name="see-also"></a>См. также

[Схемы сообщений](../../mfc/reference/message-maps-mfc.md)

