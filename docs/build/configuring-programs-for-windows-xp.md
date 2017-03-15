---
title: "Настройка программ C++ 11 для Windows XP | Microsoft Docs"
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
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Настройка программ C++ 11 для Windows XP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Так как [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] поддерживает наборы инструментов для нескольких платформ, вы можете осуществлять разработку для операционных систем и библиотек времени выполнения, которые не поддерживаются набором инструментов по умолчанию.  Например, вы можете использовать улучшения языка C\+\+11, компиляторы, библиотеки и другие компоненты, реализованные в [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], с целью создания приложений для [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Вы можете применять наборы инструментов для старых платформ, чтобы обеспечивать совместимость прежнего кода на двоичном уровне, пользуясь при этом последними возможностями интегрированной среды разработки [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
> [!NOTE]
>  Чтобы добавить поддержку наборов инструментов для платформ [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] и [!INCLUDE[winxp](../build/includes/winxp_md.md)] в [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], необходимо установить [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] с обновлением 4.  Чтобы скачать и установить копию [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] с обновлением 4, перейдите на страницу [Microsoft Visual Studio Express 2012 для Windows Desktop](http://go.microsoft.com/fwlink/?LinkID=265464) в Центре загрузки Майкрософт.  Затем установите [Visual Studio 2012 с обновлением 4](http://go.microsoft.com/fwlink/?LinkID=335900), чтобы получить набор инструментов v110\_xp.  Для получения последних обновлений ПО после установки используйте Центр обновления Windows.  
  
## Нацеливание на Windows XP  
 Набор инструментов для платформы Windows XP, включенный в [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], является версией пакета SDK [!INCLUDE[win7](../build/includes/win7_md.md)], который был включен в [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], но он использует текущий компилятор C\+\+.  Он также присваивает свойствам проекта соответствующие значения по умолчанию. Например, он задает спецификацию совместимого компоновщика для нисходящего нацеливания.  Только классические приложения Windows, созданные с помощью набора инструментов для платформы Windows XP, выполняются в [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Эти же приложения могут выполняться в более новых операционных системах, таких как Windows Vista, [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/includes/winsvr08_md.md)], [!INCLUDE[win8](../build/includes/win8_md.md)] и [!INCLUDE[winserver8](../build/includes/winserver8_md.md)].  
  
#### Нацеливание на Windows XP  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите **Свойства**.  
  
2.  В диалоговом окне **Страницы свойств** проекта откройте папку **Свойства конфигурации** и в категории **Общие** выберите для свойства **Набор инструментов платформы** нужный набор инструментов Windows XP.  Например, чтобы создать код, совместимый на двоичном уровне с распространяемыми библиотеками Microsoft Visual C\+\+ 2012, выберите **Visual Studio 2012 — Windows XP \(v110\_xp\)**.  
  
### Поддержка среды выполнения C\+\+  
 Помимо набора инструментов для платформы Windows XP, поддержка среды выполнения для [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] включена в библиотеку времени выполнения C \(CRT\), библиотеку стандартных шаблонов \(STL\), библиотеку шаблонных классов \(ATL\), библиотеку времени выполнения с параллелизмом \(ConCRT\), библиотеку параллельных шаблонов \(PPL\), библиотеку Microsoft Foundation Class \(MFC\) и среду выполнения C\+\+ AMP \(C\+\+ Accelerated Massive Programming\).  Поддерживаются следующие версии этих операционных систем: [!INCLUDE[winxp](../build/includes/winxp_md.md)] с пакетом обновления 3 \(SP3\) для x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] с пакетом обновления 2 \(SP2\) для x64 и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] c пакетом обновления 2 \(SP2\) как для x86, так и для x64.  
  
 Эти библиотеки поддерживаются наборами инструментов платформ, устанавливаемыми вместе с [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], в зависимости от целевой платформы.  
  
|Библиотека|Набор инструментов платформы по умолчанию для классических приложений Windows|Набор инструментов платформы по умолчанию для приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]|Набор инструментов платформы Windows XP для [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|  
|----------------|-----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT \- библиотека|X|X|X|  
|Библиотека STL|X|X|X|  
|ATL|X|X|X|  
|ConCRT\/PPL|X|X|X|  
|MFC|X||X|  
|C\+\+ AMP|X|X||  
  
> [!NOTE]
>  Приложения, написанные на C\+\+\/CLI и предназначенные для платформы .NET Framework 4, выполняются в [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  
  
### Различия между наборами инструментов  
 Из\-за различий в поддержке платформ и библиотек процесс разработки приложений с помощью набора инструментов платформы Windows XP не так многофункционален, как в случае с приложениями, использующими набор инструментов платформы [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] по умолчанию.  
  
-   **Возможности языка C\+\+**  
  
     В приложениях, использующих набор инструментов платформы v110\_xp, поддерживаются только те возможности языка C\+\+11, которые реализованы в [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)].  В приложениях, использующих набор инструментов платформы v120\_xp, поддерживаются только те возможности языка C\+\+11, которые реализованы в [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)].  При сборке с помощью более старых наборов инструментов платформы среда [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] использует соответствующий компилятор.  Выберите более новый набор инструментов платформы Windows XP, чтобы воспользоваться реализованными в нем дополнительными возможностями C\+\+11.  
  
-   **Удаленная отладка**  
  
     Инструменты удаленной отладки для [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] не поддерживают удаленную отладку в [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Для локальной или удаленной отладки приложения, выполняющегося в [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], можно использовать отладчик из более старой версии [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  Ситуация здесь схожа с отладкой приложений в Windows Vista, которые могут являться целью выполнения для набора инструментов платформы, но не могут являться целью удаленной отладки.  
  
-   **Статический анализ**  
  
     Наборы инструментов платформы для Windows XP не поддерживают статический анализ, так как примечания SAL для пакета SDK [!INCLUDE[win7](../build/includes/win7_md.md)] и библиотек времени выполнения несовместимы.  Если вы хотите выполнить статический анализ приложения, поддерживающего [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], вы можете временно переключиться на набор инструментов платформы по умолчанию для анализа решения, а затем вернуться к набору инструментов платформы Windows XP для сборки приложения.  
  
-   **Отладка графики DirectX**  
  
     Так как отладчик графики не поддерживает API Direct3D 9, его нельзя применять для отладки приложений, использующих Direct3D, в [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Однако если в приложении реализован альтернативный модуль прорисовки, использующий API Direct3D 10 или Direct3D 11, с помощью отладчика графики можно диагностировать проблемы с использованием этих API.  
  
-   **Сборка HLSL**  
  
     По умолчанию набор инструментов Windows XP не компилирует файлы с исходным кодом HLSL.  Для компиляции файлов HLSL скачайте и установите пакет SDK DirectX за июнь 2010 года, а затем включите его в каталоги VC проекта.  Дополнительные сведения см. в разделе «Пакет SDK DirectX не регистрирует пути включения и пути к библиотекам в Visual Studio 2010» на [странице загрузки пакета SDK DirectX за июнь 2010 года](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).