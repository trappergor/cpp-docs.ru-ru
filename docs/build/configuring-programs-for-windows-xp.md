---
title: "Настройка программ для Windows XP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff80109c1f3a5e03ecb85406cdaea24804f96783
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Настройка программ для Windows XP
Поскольку Visual Studio поддерживает несколько наборы инструментов платформы, можно ориентироваться на операционные системы и библиотек времени выполнения, которые не поддерживаются набором инструментов по умолчанию. Например, путем переключения набора инструментов платформы, можно использовать C ++ 11, C ++ 14 и улучшения C ++ 17 языков, поддерживаемых компилятором Visual C++ в Visual Studio для создания приложений, ориентированных на [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Можно также использовать более старых наборов инструментов платформы для обслуживания совместимых устаревшего кода и пользуясь при этом последними возможностями интегрированной среды разработки Visual Studio.  
  
> [!NOTE]
>  Если вы используете [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)], необходимо установить [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] обновления 4 для добавления поддержки набор инструментов платформы [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Чтобы загрузить и установить копию [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] обновление 4 см. в разделе [Microsoft Visual Studio Express 2012 для Windows Desktop](http://go.microsoft.com/fwlink/p/?linkid=265464) в центре загрузки Майкрософт. Затем установите [Visual Studio 2012 обновление 4](http://go.microsoft.com/fwlink/p/?linkid=335900) получить набор инструментов платформы v110_xp. Для получения последних обновлений ПО после установки используйте Центр обновления Windows.  
  
## <a name="windows-xp-targeting-experience"></a>Нацеливание на Windows XP  
 Набор инструментов платформы Windows XP, включенный в Visual Studio — это версия [!INCLUDE[win7](../build/includes/win7_md.md)] пакета SDK, который был включен в [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], но он использует текущий компилятор C++. Он также присваивает свойствам проекта соответствующие значения по умолчанию. Например, он задает спецификацию совместимого компоновщика для нисходящего нацеливания. Только Windows, Классические приложения, созданные с помощью набора инструментов платформы Windows XP, выполняются на [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], но эти приложения могут выполняться в более новых операционных системах Windows.  
  
#### <a name="to-target-windows-xp"></a>Нацеливание на Windows XP  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.  
  
2.  В **страницы свойств** диалогового окна "в разделе" для проекта, **свойства конфигурации**, **Общие**, задайте **набор инструментов платформы** Свойство нужный набор инструментов Windows XP. Например, выберите **Visual Studio 2015 — Windows XP (v140_xp происходит)** создание кода для [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] с помощью компилятора Microsoft Visual C++ 2015.  
  
### <a name="c-runtime-support"></a>Поддержка среды выполнения C++  
 Вместе с набора инструментов платформы Windows XP, библиотеки времени выполнения C (CRT), стандартной библиотеки C++, Active Template Library (ATL), библиотеку времени выполнения с параллелизмом (ConCRT), библиотека параллельных шаблонов (PPL), библиотека классов Microsoft Foundation (MFC) и C++ AMP (C++ Accelerated Massive программирование) Библиотека включает поддержку среды выполнения [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Для этих операционных систем, которые минимально поддерживаемые версии [!INCLUDE[winxp](../build/includes/winxp_md.md)] пакет обновления 3 (SP3) для x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] пакет обновления 2 (SP2) для x64, и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] пакет обновления 2 (SP2) для и x86- и x64.  
  
 Эти библиотеки поддерживаются наборы инструментов платформы, установленным в Visual Studio, в зависимости от целевой объект:  
  
|Библиотека|Набор инструментов платформы по умолчанию для классических приложений Windows|Набор инструментов платформы по умолчанию для приложений [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]|Набор инструментов платформы Windows XP для [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|  
|-------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT - библиотека|X|X|X|  
|Стандартная библиотека C++|X|X|X|  
|ATL|X|X|X|  
|ConCRT/PPL|X|X|X|  
|MFC|X||X|  
|C++ AMP|X|X||  
  
> [!NOTE]
>  Приложения, написанные на C++/CLI и предназначенные для платформы .NET Framework 4, выполняются в [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  
  
### <a name="differences-between-the-toolsets"></a>Различия между наборами инструментов  
 Из-за различий в поддержке платформ и библиотек процесс разработки приложений, использующих набор инструментов платформы Windows XP не так тщательна, как и для приложений, использующих набор инструментов платформы по умолчанию Visual Studio.  
  
-   **Возможности языка C++**  
  
     Только компоненты языка C++, реализованные в [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] поддерживаются в приложениях, использующих набор инструментов платформы v110_xp. Только компоненты языка C++, реализованные в [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] поддерживаются в приложениях, использующих набор инструментов платформы v120_xp. Visual Studio использует соответствующий компилятор при построении с помощью более старых наборов средств платформы. Позволяет воспользоваться преимуществами дополнительных функций языка C++, реализованными в нем компилятора последнего набора инструментов платформы Windows XP.  
  
-   **Удаленная отладка**  
  
     Инструменты удаленной отладки для Visual Studio не поддерживает удаленную отладку на [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Выполнить отладку приложения, когда она работает [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], отладчик из более старой версии Visual Studio можно использовать для его отладки, локально или удаленно. Ситуация здесь схожа с отладкой приложений в Windows Vista, которые могут являться целью выполнения для набора инструментов платформы, но не могут являться целью удаленной отладки.  
  
-   **Статический анализ**  
  
     Наборы инструментов платформы для Windows XP не поддерживают статический анализ, так как примечания SAL для пакета SDK [!INCLUDE[win7](../build/includes/win7_md.md)] и библиотек времени выполнения несовместимы. Если вы хотите выполнить статический анализ приложения, поддерживающего [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], вы можете временно переключиться на набор инструментов платформы по умолчанию для анализа решения, а затем вернуться к набору инструментов платформы Windows XP для сборки приложения.  
  
-   **Отладка графики DirectX**  
  
     Так как отладчик графики не поддерживает API Direct3D 9, его нельзя применять для отладки приложений, использующих Direct3D, в [!INCLUDE[winxp](../build/includes/winxp_md.md)] или [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Однако если в приложении реализован альтернативный модуль прорисовки, использующий API Direct3D 10 или Direct3D 11, с помощью отладчика графики можно диагностировать проблемы с использованием этих API.  
  
-   **Сборка HLSL**  
  
     По умолчанию набор инструментов Windows XP не компилирует файлы с исходным кодом HLSL. Для компиляции файлов HLSL загрузите и установите пакет SDK DirectX за июнь 2010 года, а затем включите его в каталоги VC проекта. Дополнительные сведения см. в разделе «пакет SDK DirectX не регистрирует пути включения/библиотека с Visual Studio 2010» раздела [июня 2010 г. странице загрузки пакета SDK DirectX](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).