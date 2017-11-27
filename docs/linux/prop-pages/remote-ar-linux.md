---
title: "Свойства удаленного архива (C++ Linux) | Документы Майкрософт"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.Ar.CreateIndex
- VC.Project.Ar.CreateThinArchive
- VC.Project.Ar.NoWarnOnCreate
- VC.Project.Ar.TruncateTimestamp
- VC.Project.Ar.SuppressStartupBanner
- VC.Project.Ar.Verbose
- vc.project.AdditionalOptionsPage
- VC.Project.Ar.OutputFile
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 402fa1f752b311014c828027e45a92a3dc6a2917
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="remote-archive-properties-c-linux"></a>Свойства удаленного архива (C++ Linux)

Свойство | Описание
--- | ---
Создать индекс архива | Создание индекса архива (cf. ranlib).  Это может ускорить компоновку и сократить зависимость в собственной библиотеке.
Создать тонкий архив | Создание тонкого архива.  Тонкий архив содержит относительные пути вместо встроенных объектов.  Для переключения между тонким и стандартным архивом необходимо удалить существующую библиотеку.
Без предупреждения при создании | Не предупреждать при создании библиотеки.
Обрезать метку времени | Использовать нуль для меток времени, UID и GUID.
Отключить загрузочный баннер | Не показывать номер версии.
Verbose | Verbose
Дополнительные параметры | Дополнительные параметры.
Выходной файл | Параметр /OUT переопределяет стандартное имя и место программы, создаваемые библиотекой (lib).
Архиватор | Задает программу, вызываемую при компоновке статических объектов, или путь к архиватору в удаленной системе.
Время ожидания архиватора | Время ожидания удаленного архиватора (в миллисекундах).
Копировать выходные данные | Указывает, следует ли копировать выходной файл сборки из удаленной системы на локальный компьютер.
