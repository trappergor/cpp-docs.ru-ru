---
title: Файлы предварительно скомпилированных заголовков | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- stdafx.h
dev_langs:
- C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d93486d8df8cdb8bc253a0e71037f4e2ddf9e128
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890483"
---
# <a name="precompiled-header-files"></a>Файлы предварительно скомпилированных заголовков

Эти файлы используются для построения файла предкомпилированного заголовка *Projname*.pch и файла предкомпилированных типов Stdafx.obj.

Они расположены в каталоге *Projname* . В обозревателе решений файл Stdafx.h находится в папке файлов заголовков, а Stdafx.cpp — в папке исходных файлов.

|Имя файла|Описание:|
|---------------|-----------------|
|stdafx.h|Включаемый файл для включаемых файлов стандартной системы и для определяемых проектом включаемых файлов, которые часто используются, но редко изменяются.<br /><br /> Не следует определять любые макросы _AFX_NO_XXX или отменять их определение в файле stdafx.h.|
|stdafx.cpp|Содержит директиву препроцессора `#include "stdafx.h"` и добавляет включаемые файлы для предкомпилированных типов. Предварительно скомпилированные файлы любого типа, включая файлы заголовков, могут компилироваться быстрее путем применения компиляции только к тем файлам, которые ее требуют. После построения проекта в первый раз можно заметить, что последующие сборки создаются гораздо быстрее из-за наличия файлов предкомпилированных заголовков.|

## <a name="see-also"></a>См. также

[Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Работа со свойствами проектов](../ide/working-with-project-properties.md)