---
title: Поддержка контекстов активации в состоянии модуля MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2713e0025c0587a4ab76813d4d07eed0825db447
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Поддержка контекстов активации в состоянии модуля MFC
MFC создает контекст активации с помощью ресурса манифеста, предоставляемый модулем пользователя. Дополнительные сведения о создание контекстов активации см. в следующих разделах:  
  
-   [Контексты активации](http://msdn.microsoft.com/library/aa374153)  
  
-   [Манифесты приложений](http://msdn.microsoft.com/library/aa374191)  
  
-   [Манифесты сборки](http://msdn.microsoft.com/library/aa374219)  
  
## <a name="remarks"></a>Примечания  
 При чтении в этих разделах Windows SDK, обратите внимание, что механизм контекста активации MFC напоминает контекст активации пакета SDK для Windows, за исключением того, что MFC не используют API контекст активации пакета SDK Windows.  
  
 Контекст активации работает в приложениях MFC, библиотек DLL пользователя и библиотек DLL расширения MFC одним из следующих способов:  
  
-   Приложения MFC используют идентификатор ресурса 1 для их ресурса манифеста. В этом случае MFC не создает свой собственный контекст активации, но использует контекст приложения по умолчанию.  
  
-   Пользователь MFC DLL использовать идентификатор ресурса 2 для их ресурса манифеста. Здесь MFC создает контекст активации для каждой библиотеки DLL, пользователя, поэтому другого пользователя библиотеки DLL можно использовать разные версии одной библиотек (например, в библиотеке стандартных элементов управления).  
  
-   Библиотеки DLL расширения MFC зависящие от их размещения приложения или пользователя библиотеки DLL для установления контекста активации.  
  
 Несмотря на то, что состояние контекста активации можно изменить, используя процесс, описанный в разделе [с помощью API контекст активации](http://msdn.microsoft.com/library/aa376620), механизм контекста активации MFC полезно использовать при разработке на основе DLL подключаемого модуля архитектуры Если это не просто (или невозможна) для переключения состояния активации, до и после отдельных вызовов внешних подключаемых модулей.  
  
 Контекст активации по умолчанию создается в [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit). Он будет уничтожен в `AFX_MODULE_STATE` деструктор. Дескриптор контекста активации сохраняется в `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` описан в [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)  
  
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) макрос активирует и деактивирует контекст активации по умолчанию. `AFX_MANAGE_STATE` включается для статических библиотек MFC, а также библиотеки DLL MFC, выполнение в контексте правильной активации выбранного пользователя библиотеке DLL MFC кода.  
  
## <a name="see-also"></a>См. также  
 [Контексты активации](http://msdn.microsoft.com/library/aa374153)   
 [Манифесты приложений](http://msdn.microsoft.com/library/aa374191)   
 [Манифесты сборки](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)   
 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)   
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

