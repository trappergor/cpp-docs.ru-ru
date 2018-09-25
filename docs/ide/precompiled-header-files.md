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
ms.openlocfilehash: 8d2e2bab9da3d19347577f0b1d1e8ab2ed6bb0dc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404025"
---
# <a name="precompiled-header-files"></a>Файлы предварительно скомпилированных заголовков

Эти файлы используются для построения файла предкомпилированного заголовка *Projname*.pch и файла предкомпилированных типов Stdafx.obj.

Они расположены в каталоге *Projname* . В обозревателе решений файл Stdafx.h находится в папке файлов заголовков, а Stdafx.cpp — в папке исходных файлов.

|Имя файла|Описание:|
|---------------|-----------------|
|stdafx.h|Включаемый файл для включаемых файлов стандартной системы и для определяемых проектом включаемых файлов, которые часто используются, но редко изменяются.<br /><br /> Не следует определять или отменять определение макросов _AFX_NO_XXX в файле stdafx.h: см. статью базы знаний PRB: Problems Occur When Defining _AFX_NO_XXX (PRB. При определении _AFX_NO_XXX возникают проблемы). Статьи базы знаний можно найти в библиотеке MSDN или на веб-сайте [http://support.microsoft.com/](http://%20support.microsoft.com/).|
|stdafx.cpp|Содержит директиву препроцессора `#include "stdafx.h"` и добавляет включаемые файлы для предкомпилированных типов. Предварительно скомпилированные файлы любого типа, включая файлы заголовков, могут компилироваться быстрее путем применения компиляции только к тем файлам, которые ее требуют. После построения проекта в первый раз можно заметить, что последующие сборки создаются гораздо быстрее из-за наличия файлов предкомпилированных заголовков.|

## <a name="see-also"></a>См. также

[Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Работа со свойствами проектов](../ide/working-with-project-properties.md)