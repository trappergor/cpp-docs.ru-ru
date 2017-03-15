---
title: "Пошаговое руководство. Создание приложения для Магазина Windows с использованием WRL и Media Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Пошаговое руководство. Создание приложения для Магазина Windows с использованием WRL и Media Foundation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Узнайте, как использовать [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) для создания [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] приложения, использующего [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 В этом примере создается пользовательский объект Media Foundation, который применяет эффект "оттенки серого" к изображениям, полученным с веб-камеры. Приложение использует C++ для определения пользовательского преобразования и C# для использования компонента и выполнения преобразования захваченного изображения.  
  
> [!NOTE]
>  Чтобы воспользоваться пользовательским компонентом преобразования вместо C# можно также использовать JavaScript, Visual Basic или C++.  
  
 В большинстве случаев для создания компонентов среды выполнения ([!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)]) можно использовать [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]). (Дополнительные сведения см. в разделе [Справочник по языку Visual C++](../Topic/Visual%20C++%20Language%20Reference%20\(C++-CX\).md).) Однако иногда необходимо использовать [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]. Например, при создании медиа-расширения для Microsoft Media Foundation необходимо создать компонент, реализующий одновременно модель COM и интерфейсы среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]). Поскольку [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] может создавать только объекты среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]), для создания медиа-расширения необходимо использовать библиотеку [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)], поскольку она позволяет реализовывать как модель COM, так и интерфейсы среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]).  
  
> [!NOTE]
>  Хотя этот пример кода является объемным, он показывает минимум, необходимый для создания полезных преобразований Media Foundation. Его можно использовать в качестве отправной точки для собственного пользовательского преобразования. Этот пример взят из [Пример медиа-расширений](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096), использовать медиа-расширения для применения эффектов к видео, декодирования видео и создания обработчиков схем, производящих медиа-потоки.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Опыт работы с [среды выполнения Windows](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   опыт работы с моделью COM;  
  
-   веб-камера.  
  
## <a name="key-points"></a>Ключевые моменты  
  
-   Для создания пользовательского компонента Media Foundation используйте файл определения языка MIDL, чтобы определить и реализовать интерфейс, а затем сделать его активируемым из других компонентов.  
  
-    `namespace` И `runtimeclass` атрибуты и `NTDDI_WIN8`[версии](http://msdn.microsoft.com/ru-ru/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81) значение атрибута является важной частью определения MIDL для компонента Media Foundation, который использует [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  
  
-   [Microsoft::wrl:: runtimeclass](../windows/runtimeclass-class.md) является базовым классом для пользовательского компонента Media Foundation.  [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](../windows/runtimeclasstype-enumeration.md) значение перечисления, которое передается как аргумент шаблона, помечает класс для использования как в качестве [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] класса и классического COM-класса среды выполнения.  
  
-    [InspectableClass](../windows/inspectableclass-macro.md) макрос реализует базовую функциональность модели COM, такую как подсчет ссылок и `QueryInterface` метод и задает имя класса среды выполнения и уровень доверия.  
  
-   Использовать Microsoft::WRL::[модуль класса](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe/locales/en-US) для реализации функции точки входа DLL, например [DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx), и [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx).  
  
-   Необходимо установить связь между компонентом DLL и runtimeobject.lib. Также укажите [/WINMD](../Topic/Compiler%20and%20Linker%20options%20\(C++-CX\).md) в строке компоновщика для создания метаданных Windows.  
  
-   Используйте ссылки в проекте, чтобы сделать компоненты [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] доступными для приложений, распространяемых через [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  
  
### <a name="to-use-the-includecppwrlshorttokencppwrlshortmdmd-to-create-the-media-foundation-grayscale-transform-component"></a>Создание с помощью [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] компонента преобразования Media Foundation, который применяет эффект "оттенки серого"  
  
1.  В Visual Studio создайте **пустое решение** проекта. Имя проекта, например, `MediaCapture`.  
  
2.  Добавление **DLL (приложения для магазина Windows)** проекта в решение. Имя проекта, например, `GrayscaleTransform`.  
  
3.  Добавление **Midl файл (.idl)** файл в проект. Имя файла, например, `GrayscaleTransform.idl`.  
  
4.  Добавьте в файл GrayscaleTransform.idl следующий код:  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  Замените содержимое файла pch.h следующим кодом:  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  Добавьте в проект новый файл заголовка, назовите его `BufferLock.h`, а затем добавьте следующий код:  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  Файл GrayscaleTransform.h не используется в данном примере. Его можно удалить из проекта при необходимости.  
  
8.  Замените содержимое файла GrayscaleTransform.cpp следующим кодом:  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. Добавьте в проект новый файл определения модуля, назовите его `GrayscaleTransform.def`, а затем добавьте следующий код:  
  
     [!CODE [wrl-media-capture#5](../CodeSnippet/VS_Snippets_Misc/wrl-media-capture#5)]  
  
10. Замените содержимое файла dllmain.cpp следующим кодом:  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. В проекте **страницы свойств** диалоговом окне задайте следующие **компоновщика** Свойства.  
  
    1.  В разделе **ввода**, для **файл определения модуля**, укажите `GrayScaleTransform.def`.  
  
    2.  Также в разделе **ввода**, добавление `runtimeobject.lib`, `mfuuid.lib`, и `mfplatf.lib` для **Дополнительные зависимости** свойство.  
  
    3.  В разделе **метаданных Windows**, задайте **создания метаданных Windows** для **Да (/ WINMD)**.  
  
### <a name="to-use-the-includecppwrlshorttokencppwrlshortmdmd-the-custom-media-foundation-component-from-a-c-app"></a>Создание пользовательского компонента Media Foundation из приложения C# с помощью [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]  
  
1.  Добавить новую **C# пустое приложение (XAML)** проект `MediaCapture` решения. Имя проекта, например, `MediaCapture`.  
  
2.  В **MediaCapture** проекта, добавьте ссылку на `GrayscaleTransform` проекта. Сведения см. в разделе [Практическое руководство: Добавление и удаление ссылок с помощью диспетчера ссылок](../Topic/How%20to:%20Add%20or%20Remove%20References%20By%20Using%20the%20Reference%20Manager.md).  
  
3.  В Package.appxmanifest на **возможности** выберите **микрофон** и **веб-камера**. Обе возможности необходимы для получения фотографий с веб-камеры.  
  
4.  В файле MainPage.xaml, добавьте следующий код в корне [сетки](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) элемента:  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  Замените содержимое файла MainPage.xaml.cs следующим кодом:  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 На следующем рисунке показано приложение MediaCapture.  
  
 ![Приложение MediaCapture, захватывающее фотографию](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Пример показывает способ записи фотографий (по одной) с веб-камеры по умолчанию.  [Пример медиа-расширений](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) дополнительных. В нем показано, как выполнить перебор веб-камер и работать с локальными обработчиками схем, а также демонстрируются дополнительные медиа-эффекты, работающие как на отдельных фотографиях, так и на потоках видео.  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)   
 [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [Пример медиа-расширений](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)