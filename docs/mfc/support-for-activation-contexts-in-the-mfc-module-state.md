---
title: Поддержка контекстов активации в состоянии модуля MFC
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: c5e3d5c9195f18c54de63ec7ecd38b165feca5df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619027"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Поддержка контекстов активации в состоянии модуля MFC

MFC создает контекст активации с помощью ресурса манифеста, предоставляемых модулем пользователя. Дополнительные сведения о создании контекстов активации см. в разделах:

- [Контексты активации](/windows/desktop/SbsCs/activation-contexts)

- [Манифесты приложений](/windows/desktop/SbsCs/application-manifests)

- [Манифесты сборки](/windows/desktop/SbsCs/assembly-manifests)

## <a name="remarks"></a>Примечания

При чтении в этих разделах пакета SDK для Windows, обратите внимание, что механизм контекста активации MFC напоминает контекст активации Windows SDK, за исключением того, что MFC не используют API контекст активации для Windows SDK.

Контекст активации работает в приложениях MFC, пользователя библиотеки DLL и библиотеки DLL расширения MFC одним из следующих способов:

- Приложения MFC использовать идентификатор ресурса 1 для их ресурса манифеста. В этом случае MFC не создает свой собственный контекст активации, но использует контекст приложения по умолчанию.

- Пользователь MFC DLL использовать идентификатор ресурса 2 для их ресурса манифеста. Здесь MFC создает контекст активации для каждой библиотеки DLL, пользователя, поэтому другого пользователя библиотеки DLL могут использовать разные версии одних библиотек (например, библиотека стандартных элементов управления).

- Библиотеки DLL расширения MFC зависят от их размещения приложения или пользователя библиотеки DLL для установления контекста активации.

Несмотря на то, что состояние контекста активации можно изменить с помощью процессов, описанные в разделе [с помощью API контекст активации](/windows/desktop/SbsCs/using-the-activation-context-api), с помощью механизма контекст активации MFC можно использовать при разработке на основе DLL подключаемого модуля архитектур Если это не просто (или невозможна) для переключения состояния активации до и после отдельных вызовов внешних подключаемых модулей.

Контекст активации создается в [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit). Он будет уничтожен в `AFX_MODULE_STATE` деструктор. Дескриптор контекста активации сохраняется в `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` описан в [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)

[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) макрос активирует и деактивирует контекст активации. `AFX_MANAGE_STATE` предусмотрена поддержка статические библиотеки MFC, а также библиотеки DLL MFC, чтобы разрешить коду MFC, выполняются в контексте правильной активации выбранного библиотекой пользователя.

## <a name="see-also"></a>См. также

[Контексты активации](/windows/desktop/SbsCs/activation-contexts)<br/>
[Манифесты приложений](/windows/desktop/SbsCs/application-manifests)<br/>
[Манифесты сборки](/windows/desktop/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

