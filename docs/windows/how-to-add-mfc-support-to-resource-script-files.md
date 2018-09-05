---
title: 'Практическое: Добавление поддержки MFC в файлы описания ресурсов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.add.MFC
dev_langs:
- C++
helpviewer_keywords:
- rc files, adding MFC support
- .rc files, adding MFC support
- MFC, adding support to resource scripts files
- resource script files, adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 194f2b4f2e6659412c9c2b5f688e0b73eea3bba5
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692032"
---
# <a name="how-to-add-mfc-support-to-resource-script-files"></a>Практическое руководство. Добавление поддержки MFC в файлы описания ресурсов

Как правило, при создании приложения MFC для Windows с помощью [мастер приложений MFC](../mfc/reference/mfc-application-wizard.md), мастер создает базовый набор файлов (включая RC-файл ресурсов), который включает основные функции Microsoft Foundation классы (MFC). Однако при редактировании RC-файла для приложения Windows, в основе которого не лежит MFC, будут недоступны следующие возможности, предназначенные для платформы MFC.

- Мастеры кода MFC

- Строки подсказок для меню.

- Содержимое списков для элементов управления "поле со списком".

- Размещение элементов управления ActiveX.

Тем не менее можно добавить поддержку MFC для существующих RC-файлов, которые ее не имеют.

### <a name="to-add-mfc-support-to-rc-files"></a>Добавление поддержки MFC в RC-файлы

1. Откройте файл описания ресурсов.

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В [представление ресурсов](../windows/resource-view-window.md), выделите папку ресурсов (например, MFC.rc).

3. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), задайте **режим MFC** свойства **True**.

   > [!NOTE]
   > Кроме того, что будет установлен этот флаг, RC-файл должен быть частью проекта MFC. Например, просто задав **режим MFC** для **True** на RC-файла в Win32 проект не станут доступными функции MFC.

## <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редакторы ресурсов](../windows/resource-editors.md)