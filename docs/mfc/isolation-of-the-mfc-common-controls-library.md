---
title: "Изоляция MFC Общие элементы управления библиотеки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04ed1be46d4c3d7f36bfa501bfc933fbba41e8d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Изоляция библиотеки общих элементов управления MFC
Библиотека стандартных элементов управления теперь изолирована в MFC, позволяя различных модулей (например, пользователь библиотек DLL) используют разные версии библиотеки общих элементов управления с указанием версии в манифестах.  
  
 Приложение MFC (или пользовательского кода, вызываемого MFC) выполняет вызовы интерфейсов API через функции-оболочки с именем библиотеки общих элементов управления `Afx` *FunctionName*, где *FunctionName* обычное имя Элементы управления API. Эти функции-оболочки определяются в afxcomctl32.h и afxcomctl32.inl.  
  
 Можно использовать [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) и [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) макросы (определенные в afxcomctl32.h) для определения того, реализует ли общие элементы управления библиотеки определенных API вместо вызова метода [GetProcAddress](../build/getprocaddress.md).  
  
 С технической точки зрения выполнять вызовы API-интерфейсы библиотеки общих элементов управления через класс-оболочку `CComCtlWrapper` (определенная в afxcomctl32.h). `CComCtlWrapper`Кроме того отвечает за загрузку и выгрузку comctl32.dll. Состояния модуля MFC содержит указатель на экземпляр `CComCtlWrapper`. Доступ к класса программы-оболочки с помощью `afxComCtlWrapper` макрос.  
  
 Обратите внимание, что вызов общий API управления непосредственно (не с помощью функции-оболочки MFC) из MFC приложением или пользователем DLL будет работать в большинстве случаев, так как приложение MFC или пользовательской библиотеки DLL привязана к библиотеке стандартных элементов управления, она запрошена в манифесте). Тем не менее сам код MFC должен использовать программы-оболочки, так как код MFC можно вызвать из библиотек DLL пользователей с разными версиями библиотеки общих элементов управления.

