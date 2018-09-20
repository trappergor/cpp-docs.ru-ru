---
title: С помощью мастера MFC DLL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.dll.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], creating
- MFC DLL Wizard
- DLLs [MFC], MFC
- DLL wizard [MFC]
- MFC DLLs [MFC]
- DLLs [MFC], creating
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8218500fc17efda01b4ecaa11b6ebf12bd76812
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436277"
---
# <a name="mfc-dll-wizard"></a>мастер DLL [MFC]

При использовании мастера MFC DLL для создания проекта MFC DLL, вы получаете работающее приложение со встроенной функциональностью, после компиляции будет реализовывать основные возможности [DLL](../../build/dlls-in-visual-cpp.md). Начальная программа MFC включает в себя (.cpp) исходные файлы C++, файлы ресурсов (.rc) и файл проекта (VCXPROJ-файл). Код, созданный в этих начальный набор файлов зависит от MFC. Дополнительные сведения см. в разделе о файлах файла readme.txt, которая создается для проекта в Visual Studio и [классы и функции, созданных с помощью мастера MFC DLL](../../mfc/reference/classes-and-functions-generated-by-the-mfc-dll-wizard.md)

## <a name="overview"></a>Обзор

На этой странице мастера описываются текущего [параметры приложения для проекта библиотеки DLL MFC](../../mfc/reference/application-settings-mfc-dll-wizard.md) вы создаете. По умолчанию проект создается как обычный проект библиотеки DLL MFC (MFC Shared) без дополнительных параметров.

Чтобы изменить эти значения по умолчанию, нажмите кнопку **параметры приложения** в левом столбце мастера и внести изменения на странице мастера MFC DLL.

После создания проекта MFC DLL, можно добавить объекты и элементы управления в проект с помощью Visual C++ [кода мастеров](../../ide/adding-functionality-with-code-wizards-cpp.md).

Можно выполнять следующие задачи и типы расширений для базовый проект библиотеки DLL MFC.

- [Экспорт из библиотеки DLL](../../build/exporting-from-a-dll.md)

- [Связывание исполняемого файла с библиотекой DLL](../../build/linking-an-executable-to-a-dll.md)

- [Инициализация библиотеки DLL](../../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="see-also"></a>См. также

[Создание проектов Visual C++ и управление ими](../../ide/creating-and-managing-visual-cpp-projects.md)<br/>
[Страницы свойств](../../ide/property-pages-visual-cpp.md)<br/>
[Работа со свойствами проектов](../../ide/working-with-project-properties.md)<br/>
[Класс MFC](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Реализация интерфейса](../../ide/implementing-an-interface-visual-cpp.md)<br/>
[Поддержка мастера для других языков](../../ide/wizard-support-for-other-languages.md)

