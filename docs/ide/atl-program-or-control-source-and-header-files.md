---
title: "Программа ATL или управление файлами исходного кода и заголовков | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы файлов [C++], ATL - ресурсы и заголовки"
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Программа ATL или управление файлами исходного кода и заголовков
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании проектов ATL в Visual Studio, в зависимости от выбранных параметров для создаваемого проекта, создаются следующие файлы.  
  
 Все эти файлы расположены в каталоге *Projname* и либо в папке с файлами заголовка \(H\-файлы\), либо в папке с исходными файлами \(CPP\-файлы\) в обозревателе решений.  
  
|Имя файла|Описание|  
|---------------|--------------|  
|*Projname*.h|Основной файл, в котором содержатся определения интерфейса С\+\+ и объявления идентификаторов GUID элементов, определенных в файле ATLSample.idl.  Заново создается MIDL во время компиляции.|  
|*Projname*.cpp|Исходный файл основной программы.  Содержит реализацию экспортированных библиотек DLL для внутрипроцессного сервера и реализацию `WinMain` для локального сервера.  Также дополнительно реализует все функции управления службами.|  
|Resource.h|Файл заголовка для файла ресурса.|  
|StdAfx.cpp|Содержит файлы StdAfx.h и Atlimpl.cpp.|  
|StdAfx.h|Содержит файлы заголовков ATL.|  
  
## См. также  
 [Типы файлов, создаваемых для проектов Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Программа MFC или управление файлами исходного кода и заголовков](../ide/mfc-program-or-control-source-and-header-files.md)   
 [Проекты CLR](../ide/files-created-for-clr-projects.md)