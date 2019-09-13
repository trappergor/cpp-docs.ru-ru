---
title: Поддержка контекстов активации в состоянии модуля MFC
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: 296df3d2ecec74c5c9a7deef1617298d40243724
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511432"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Поддержка контекстов активации в состоянии модуля MFC

MFC создает контекст активации, используя ресурс манифеста, предоставленный модулем пользователя. Дополнительные сведения о создании контекстов активации см. в следующих разделах:

- [Контексты активации](/windows/win32/SbsCs/activation-contexts)

- [Манифесты приложений](/windows/win32/SbsCs/application-manifests)

- [Манифесты сборки](/windows/win32/SbsCs/assembly-manifests)

## <a name="remarks"></a>Примечания

При чтении этих Windows SDKых разделов Обратите внимание, что механизм контекста активации MFC напоминает контекст активации Windows SDK, за исключением того, что MFC не использует API контекста активации Windows SDK.

Контекст активации работает в приложениях MFC, библиотеках DLL пользователей и библиотеках DLL расширения MFC следующим образом:

- Приложения MFC используют идентификатор ресурса 1 для ресурса манифеста. В этом случае MFC не создает собственный контекст активации, но использует контекст приложения по умолчанию.

- Библиотеки DLL пользователей MFC используют идентификатор ресурса 2 для ресурса манифеста. В этом случае MFC создает контекст активации для каждой пользовательской библиотеки DLL, поэтому разные пользовательские библиотеки могут использовать разные версии одних и тех же библиотек (например, библиотеку Common Controls).

- Библиотеки DLL расширения MFC используют приложения размещения или пользовательские библиотеки DLL для установки контекста активации.

Несмотря на то, что состояние контекста активации можно изменить с помощью процессов, описанных в разделе [Использование API контекста](/windows/win32/SbsCs/using-the-activation-context-api)активации, использование механизма контекста активации MFC может оказаться полезным при разработке архитектур подключаемых модулей на основе библиотек DLL, где это непросто (или невозможно) для переключения состояния активации вручную до и после отдельных вызовов внешних подключаемых модулей.

Контекст активации создается в [афксвининит](../mfc/reference/application-information-and-management.md#afxwininit). Он уничтожается в `AFX_MODULE_STATE` деструкторе. Обработчик контекста активации хранится в `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` описывается в [афксжетстатикмодулестате](reference/extension-dll-macros.md#afxgetstaticmodulestate).)

Макрос [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) активирует и деактивирует контекст активации. `AFX_MANAGE_STATE`включается для статических библиотек MFC, а также библиотек DLL MFC, чтобы код MFC выполнялся в правильном контексте активации, выбранном в библиотеке DLL пользователя.

## <a name="see-also"></a>См. также

[Контексты активации](/windows/win32/SbsCs/activation-contexts)<br/>
[Манифесты приложений](/windows/win32/SbsCs/application-manifests)<br/>
[Манифесты сборки](/windows/win32/SbsCs/assembly-manifests)<br/>
[афксвининит](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[афксжетстатикмодулестате](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
