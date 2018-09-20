---
title: Обработчики полей со списками | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_CBN_KILLFOCUS
- ON_CBN_ERRSPACE
- ON_CBN_EDITCHANGE
- ON_CBN_CLOSEUP
- ON_CBN_DBLCLK
- ON_CBN_EDITUPDATE
- ON_CBN_DROPDOWN
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
- ON_CBN_SETFOCUS
- ON_CBN_SELENDCANCEL
dev_langs:
- C++
helpviewer_keywords:
- ON_CBN_CLOSEUP
- ON_CBN_SETFOCUS
- ON_CBN_DBLCLK
- ON_CBN_SELENDCANCEL
- ON_CBN_DROPDOWN
- ON_CBN_EDITUPDATE
- ON_CBN_KILLFOCUS
- combo boxes [MFC], handlers
- ON_CBN_EDITCHANGE
- ON_CBN_ERRSPACE
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5751fbdd4bff0cf3d42231ad00bef0c3483ccfb9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424265"
---
# <a name="combo-box-handlers"></a>Обработчики полей со списками

Прототипы функции соответствуют следующие записи карты.

|Запись сопоставления|Прототип функции|
|---------------|------------------------|
|ON_CBN_CLOSEUP ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn)|
|ON_CBN_DBLCLK ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_DROPDOWN ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_EDITCHANGE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_EDITUPDATE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_ERRSPACE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_KILLFOCUS ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_SELCHANGE ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_SELENDCANCEL ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_SELENDOK ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|
|ON_CBN_SETFOCUS ( \<идентификатор >, \<memberFxn >)|(afx_msg void memberFxn);|

## <a name="see-also"></a>См. также

[Схемы сообщений](../../mfc/reference/message-maps-mfc.md)

