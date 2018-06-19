---
title: Изоляция MFC Общие элементы управления библиотеки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 193a0ea527cda3819a585f5b7149c823a7eb8ef7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346819"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Изоляция библиотеки общих элементов управления MFC
Библиотека стандартных элементов управления теперь изолирована в MFC, позволяя различных модулей (например, пользователь библиотек DLL) используют разные версии библиотеки общих элементов управления с указанием версии в манифестах.  
  
 Приложение MFC (или пользовательского кода, вызываемого MFC) выполняет вызовы интерфейсов API через функции-оболочки с именем библиотеки общих элементов управления `Afx` *FunctionName*, где *FunctionName* обычное имя Элементы управления API. Эти функции-оболочки определяются в afxcomctl32.h и afxcomctl32.inl.  
  
 Можно использовать [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) и [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) макросы (определенные в afxcomctl32.h) для определения того, реализует ли общие элементы управления библиотеки определенных API вместо вызова метода [GetProcAddress](../build/getprocaddress.md).  
  
 С технической точки зрения выполнять вызовы API-интерфейсы библиотеки общих элементов управления через класс-оболочку `CComCtlWrapper` (определенная в afxcomctl32.h). `CComCtlWrapper` Кроме того отвечает за загрузку и выгрузку comctl32.dll. Состояния модуля MFC содержит указатель на экземпляр `CComCtlWrapper`. Доступ к класса программы-оболочки с помощью `afxComCtlWrapper` макрос.  
  
 Обратите внимание, что вызов общий API управления непосредственно (не с помощью функции-оболочки MFC) из MFC приложением или пользователем DLL будет работать в большинстве случаев, так как приложение MFC или пользовательской библиотеки DLL привязана к библиотеке стандартных элементов управления, она запрошена в манифесте). Тем не менее сам код MFC должен использовать программы-оболочки, так как код MFC можно вызвать из библиотек DLL пользователей с разными версиями библиотеки общих элементов управления.

