---
title: Программа ATL или управление файлами исходного кода и заголовков
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: 15d49cf984e45feeaad454de13c4ab37622000a4
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446578"
---
# <a name="atl-program-or-control-source-and-header-files"></a>Программа ATL или управление файлами исходного кода и заголовков

Следующие файлы создаются при создании проекта ATL в Visual Studio с учетом от выбранных для него параметров.

Все эти файлы находятся в каталоге *Имя_проекта* и в папке файлов заголовков (H) или исходных файлов (CPP) в обозревателе решений.

|Имя файла|Описание|
|---------------|-----------------|
|*Имя_проекта*.h|Основной включаемый файл, содержащий определения интерфейса C++ и объявления идентификаторов GUID для элементов, определенных в файле ATLSample.idl. MIDL создает его повторно во время компиляции.|
|*Имя_проекта*.cpp|Исходный файл основной программы. Он содержит реализацию операций экспорта библиотеки DLL для внутрипроцессного сервера и реализацию `WinMain` для локального сервера. Для службы дополнительно реализуются все функции управления службами.|
|Resource.h|Файл заголовка для файла ресурсов.|
|StdAfx.cpp|Содержит файлы StdAfx.h и Atlimpl.cpp.|
|StdAfx.h|Содержит файлы заголовков ATL.|

## <a name="see-also"></a>См. также

[Файл создавать типы для визуального C++ проектов](file-types-created-for-visual-cpp-projects.md)<br>
[Программа MFC или управление файлами исходного кода и заголовков](mfc-program-or-control-source-and-header-files.md)<br>
[Проекты CLR](files-created-for-clr-projects.md)
