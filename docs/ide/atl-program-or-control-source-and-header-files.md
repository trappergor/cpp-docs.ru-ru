---
title: Программа ATL или управление файлами исходного кода и заголовков | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95fa6fa506e4f471b90d39659b0908e2755b72b0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398707"
---
# <a name="atl-program-or-control-source-and-header-files"></a>Программа ATL или управление файлами исходного кода и заголовков

Следующие файлы создаются при создании проекта ATL в Visual Studio с учетом от выбранных для него параметров.

Все эти файлы находятся в каталоге *Имя_проекта* и в папке файлов заголовков (H) или исходных файлов (CPP) в обозревателе решений.

|Имя файла|Описание:|
|---------------|-----------------|
|*Имя_проекта*.h|Основной включаемый файл, содержащий определения интерфейса C++ и объявления идентификаторов GUID для элементов, определенных в файле ATLSample.idl. MIDL создает его повторно во время компиляции.|
|*Имя_проекта*.cpp|Исходный файл основной программы. Он содержит реализацию операций экспорта библиотеки DLL для внутрипроцессного сервера и реализацию `WinMain` для локального сервера. Для службы дополнительно реализуются все функции управления службами.|
|Resource.h|Файл заголовка для файла ресурсов.|
|StdAfx.cpp|Содержит файлы StdAfx.h и Atlimpl.cpp.|
|StdAfx.h|Содержит файлы заголовков ATL.|

## <a name="see-also"></a>См. также

[Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Программа MFC или управление файлами исходного кода и заголовков](../ide/mfc-program-or-control-source-and-header-files.md)<br>
[Проекты CLR](../ide/files-created-for-clr-projects.md)