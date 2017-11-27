---
title: "Свойства настраиваемого этапа сборки (Linux C++) | Документы Майкрософт"
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.Description
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 77d483e9d4dc74cbe9ba2736a26561bb410fa6ca
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="custom-build-step-properties-linux-c"></a>Свойства настраиваемого этапа сборки (Linux C++)


Свойство | Описание
--- | ---
Командная строка | Команда, которая будет выполняться этим пользовательским действием сборки.
Описание | Сообщение, которое отображается при выполнении пользовательского действия сборки.
Вывод | Выходной файл, создаваемый пользовательским действием сборки. Этот параметр является обязательным для правильной работы добавочных сборок.
Дополнительные зависимости | Разделенный точками с запятой список каких-либо дополнительных входных файлов для пользовательского действия сборки.
Выполнить после и выполнить до | Эти параметры определяют, когда пользовательское действие сборки выполняется в процессе сборки относительно перечисленных целевых объектов. Наиболее часто в число целевых объектов входят BuildGenerateSources, BuildCompile и BuildLink, поскольку они представляют основные этапы процесса сборки. Другие часто используемые целевые объекты: Midl, CLCompile и Link.
Обрабатывать выходные данные как содержимое | Этот параметр имеет значение только для приложений Магазина Windows и Windows Phone, включающих все файлы содержимого в пакет .appx.