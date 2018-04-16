---
title: Состояния модулей обычной MFC DLL, динамически компонуемые с MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b88f895255c698f04b6988e63b8b75372fa59b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>Состояния модулей обычной MFC DLL, динамически компонуемые с MFC
Возможность динамически связывать регулярных MFC DLL с библиотекой DLL MFC позволяет некоторые очень сложные конфигурации. Например регулярных DLL MFC и исполняемый файл, который его использует могут динамически связаться с библиотекой DLL MFC и для любого расширения MFC библиотеки DLL.  
  
 Эта конфигурация создает проблему по отношению к глобальным данным MFC, такие как указатель на текущий `CWinApp` объекта и сопоставления дескрипторов.  
  
 Перед MFC версии 4.0 глобальные данные хранились в самой библиотеке DLL MFC и были общими для всех модулей процесса. Так как каждый процесс, использующий библиотеку DLL Win32 получает собственную копию данных DLL, подобная схема предоставляет простой способ отслеживания данных каждого процесса. Кроме того так как модель AFXDLL предполагает, что существует только один `CWinApp` объект и только один набор сопоставлений в процессе дескрипторов, эти элементы можно отследить в самой библиотеке DLL MFC.  
  
 Но возможность динамического связывания регулярных DLL MFC с библиотекой DLL MFC, стало возможно наличие двух или более `CWinApp` объекты в процессе, а также нескольких наборов сопоставлений дескрипторов. Как MFC хранить список какие из них следует использовать?  
  
 Решения — предоставить собственную копию этой информации глобальное состояние каждого модуля (приложению или обычной MFC DLL). Таким образом, вызов **AfxGetApp** в регулярных MFC DLL возвращает указатель на `CWinApp` объект в DLL, а не один в исполняемом файле. Эта копия-module глобальных данных MFC называется состоянием модуля и рассматривается в [Техническая заметка MFC 58](../mfc/tn058-mfc-module-state-implementation.md).  
  
 Общая процедура окна MFC автоматически переключается на верное состояние модуля, поэтому не нужно беспокоиться в любой обработчиков сообщений, реализованных в обычной DLL MFC. Но когда исполняемый файл вызывает обычную библиотеку DLL MFC, необходимо явно задать текущее состояние модуля в одну из библиотек DLL. Чтобы сделать это, используйте **AFX_MANAGE_STATE** макрос в каждой функции, экспортированные из библиотеки DLL. Это можно сделать, добавив следующую строку кода в начало функции, экспортированные из библиотеки DLL:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Обычные библиотеки DLL MFC, динамически компонуемые с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Библиотеки DLL расширений MFC](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)