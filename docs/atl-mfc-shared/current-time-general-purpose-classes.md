---
title: 'Текущее время: Классы общего назначения | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9edf381864121d4e3f6c5a2b6cf7c01198368e1e
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860528"
---
# <a name="current-time-general-purpose-classes"></a>Текущее время: Классы общего назначения

Ниже показано, как создать `CTime` и инициализируйте его с текущим временем.

### <a name="to-get-the-current-time"></a>Чтобы получить текущее время

1. Выделить `CTime` объекта, как показано ниже:

   [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]

   > [!NOTE]
   > Неинициализированный `CTime` объекты не инициализируются в допустимое время.

1. Вызовите `CTime::GetCurrentTime` функцию, чтобы получить текущее время из операционной системы. Эта функция возвращает `CTime` объект, который может использоваться для задания значения `CTime`, как показано ниже:

   [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]

   Так как `GetCurrentTime` — это статическая функция-член из `CTime` класса, необходимо указать его имя с именем класса и оператора разрешения области действия (`::`), `CTime::GetCurrentTime()`.

Само собой два действия, описанные ранее можно объединить в одну инструкцию программы следующим образом:

[!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]
