---
title: "Программа ATL или управление исходного кода и файлов заголовков | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a13a4c6ddb74a6f63b5da1171a3d4360199b508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-program-or-control-source-and-header-files"></a>Программа ATL или управление файлами исходного кода и заголовков
Следующие файлы создаются при создании проекта ATL в Visual Studio, в зависимости от параметров, выбранных для создаваемого проекта.  
  
 Все эти файлы расположены в *Projname* каталог и в папке файлов заголовков (h-файлы) или в папку исходных файлов (CPP-файлы) в обозревателе решений.  
  
|Имя файла|Описание:|  
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