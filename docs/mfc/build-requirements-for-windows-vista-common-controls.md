---
title: "Требования к сборке для стандартных элементов управления Windows Vista | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76919bcdd416ed7195e94ed1fa0b2e3f3a4d573d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Требования к сборке для использования стандартных элементов управления в Windows Vista
Библиотека Microsoft Foundation Class (MFC) поддерживает стандартные элементы управления Windows версии 6.1. Стандартные элементы управления, включенные в [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] и включается в библиотеке [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]. Эта библиотека предоставляет новые методы, которые повышают существующих классов и новые классы и методы, поддерживающие [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] стандартных элементов управления. При построении приложения необходимо соблюдать требования к компиляции и миграции, описанные в следующих разделах.  
  
## <a name="compilation-requirements"></a>Требованиями к компиляции  
  
### <a name="supported-versions"></a>Поддерживаемые версии  
 Некоторые новые классы и методы поддерживают только [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] и более поздней версии, то время как другие методы также поддерживать более ранних операционных систем. Примечание в `Requirements` каждого раздела метод указывает, когда Минимальная требуемая операционная система является [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)].  
  
 Даже если компьютер не запускается [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)], можно построить приложение MFC, который будет выполняться на [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] при наличии на компьютере файлы заголовков MFC версии 6.1. Тем не менее, общие элементы управления, предназначенные специально для [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] работать только с этой системы и более ранних операционных систем, учитываются.  
  
### <a name="supported-character-sets"></a>Поддерживаемые кодировки  
 Новые общие элементы управления Windows поддерживает только кодировки Юникод, а не набора знаков ANSI. При построении приложения в командной строке используйте оба следующих определяют (/ D) параметры компилятора для указания Юникода как базовый набор символов:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 При создании приложения в среде разработки Visual Studio (IDE), укажите **набор символов Юникода** параметр **кодировки** свойства **Общие**  узел свойств проекта.  
  
 Версия ANSI из нескольких методов MFC являются устаревшими начиная с общих элементах управления Windows версии 6.1. Дополнительные сведения см. в разделе [устаревшие интерфейсы API ANSI](../mfc/deprecated-ansi-apis.md).  
  
## <a name="migration-requirements"></a>Требования для миграции  
 При использовании интегрированной среды разработки Visual Studio для создания нового приложения MFC, которое использует стандартные элементы управления Windows версии 6.1, интегрированная среда разработки автоматически объявляет соответствующий манифест. Тем не менее если необходимо перенести существующее приложение MFC из более ранней версии Visual Studio, а вы хотите использовать новые общие элементы управления, интегрированной среды разработки не предоставляет автоматически манифеста информации для обновления приложения. Вместо этого необходимо вручную вставить следующий исходный код в файле stdafx.h:  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## <a name="see-also"></a>См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [Диаграмма иерархии](../mfc/hierarchy-chart.md)   
 [Нерекомендуемые API ANSI](../mfc/deprecated-ansi-apis.md)

