---
title: Программа ATL или управление исходного кода и файлов заголовков | Документы Microsoft
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
ms.openlocfilehash: 3e8e5065cebab002e9c48aef560eb9f2feab67e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="atl-program-or-control-source-and-header-files"></a>Программа ATL или управление файлами исходного кода и заголовков
Следующие файлы создаются при создании проекта ATL в Visual Studio, в зависимости от параметров, выбранных для создаваемого проекта.  
  
 Все эти файлы расположены в *Projname* каталог и в папке файлов заголовков (h-файлы) или в папку исходных файлов (CPP-файлы) в обозревателе решений.  
  
|Имя файла|Описание|  
|---------------|-----------------|  
|*ProjName*.h|Основной файл определения интерфейса C++ и объявления идентификаторов GUID для элементов, определенных в файле ATLSample.idl. Заново создается MIDL во время компиляции.|  
|*ProjName*.cpp|Исходный файл основной программы. Он содержит реализацию экспорта библиотеки DLL для внутрипроцессного сервера и реализация `WinMain` для локального сервера. Для службы Дополнительно реализует все функции управления службами.|  
|Resource.h|Файл заголовка для файла ресурсов.|  
|StdAfx.cpp|Содержит файлы, StdAfx.h и Atlimpl.cpp.|  
|StdAfx.h|Включает файлы заголовков ATL.|  
  
## <a name="see-also"></a>См. также  
 [Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Программа MFC или системы управления версиями и файлы заголовков](../ide/mfc-program-or-control-source-and-header-files.md)   
 [Проекты CLR](../ide/files-created-for-clr-projects.md)