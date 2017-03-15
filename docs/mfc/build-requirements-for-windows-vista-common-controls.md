---
title: "Требования к сборке для использования стандартных элементов управления в Windows Vista | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "стандартные элементы управления (MFC)"
  - "стандартные элементы управления (MFC), требования к сборке"
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Требования к сборке для использования стандартных элементов управления в Windows Vista
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотеки Microsoft Foundation Class \(MFC\) версии 6.1 поддерживает общих элементов управления Windows.  Стандартные элементы управления входят в состав [!INCLUDE[windowsver](../Token/windowsver_md.md)] и библиотека включена в [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)].  Библиотека предоставляет новые методы, которые расширяют существующие классы, а новые классы и методы, которые поддерживают общие элементы управления [!INCLUDE[windowsver](../Token/windowsver_md.md)].  При построении приложения необходимо выполнить требования к компиляции и миграции, которые описаны в следующих разделах.  
  
## Требования к компиляции  
  
### Поддерживаемые версии  
 Некоторые новые классы и методы поддерживают только [!INCLUDE[windowsver](../Token/windowsver_md.md)] и более поздних версиях, а другие методы также поддерживают более ранние версии операционных систем.  Примечание в раздел `Requirements` каждого раздела метода определяет, когда требуемая минимальная операционной системы [!INCLUDE[windowsver](../Token/windowsver_md.md)].  
  
 Даже если компьютер не используется [!INCLUDE[windowsver](../Token/windowsver_md.md)], можно построить приложение MFC, которая выполняется в [!INCLUDE[windowsver](../Token/windowsver_md.md)], если имеется файлы заголовков MFC версии 6.1 на компьютере.  Однако общие элементы управления, которые разработаны специально для [!INCLUDE[windowsver](../Token/windowsver_md.md)] работают только в этой системе и игнорируются предыдущих операционными системами.  
  
### Поддерживаемые кодировки  
 Стандартные элементы управления нового окна поддерживают только набор символ юникода и не набор символов ANSI.  При построении приложения в командной строке следует использовать оба следующих указать параметры компилятора \(\/D\) для указания кодировки юникод в качестве основной:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 При построении приложения в интегрированной среде разработки Visual Studio \(IDE\), укажите параметр **Символ юникода набор** свойства **Набор символов** в узле **Общие** свойств проекта.  
  
 Версия ANSI нескольких методов MFC выступанный против начиная с версии 6.1 общих элементов управления Windows.  Для получения дополнительной информации см. [Нерекомендуемые API ANSI](../mfc/deprecated-ansi-apis.md).  
  
## Требования к миграции  
 При использовании интегрированной среды разработки Visual Studio, чтобы создать новое приложение, MFC, использует версию 6.1 общих элементов управления Windows, интегрированная среда разработки автоматически объявляет соответствующий манифест.  Однако при миграции существующее приложение MFC из более ранней версии Visual Studio и требуется использовать новых общих элементов управления, интегрированная среда разработки автоматически не предоставляет сведения о манифесте для обновления приложения.  Вместо этого необходимо вручную добавить следующий исходный код в файл stdafx.h:  
  
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
  
## См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [Диаграмма иерархии](../mfc/hierarchy-chart.md)   
 [Нерекомендуемые API ANSI](../mfc/deprecated-ansi-apis.md)