---
title: 'Пошаговое руководство: Создание приложения универсальной платформы Windows, с использованием WRL и Media Foundation | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6db5f5eb080f9d802090dda61afd296bc4e6dc3b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015047"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Пошаговое руководство: Создание приложения универсальной платформы Windows, с использованием WRL и Media Foundation
Сведения об использовании Windows шаблонов среды выполнения C++ Library (WRL), чтобы создать приложение универсальной платформы Windows (UWP), которое использует [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 В этом примере создается пользовательский объект Media Foundation, который применяет эффект "оттенки серого" к изображениям, полученным с веб-камеры. Приложение использует C++ для определения пользовательского преобразования и C# для использования компонента и выполнения преобразования захваченного изображения.  
  
> [!NOTE]
>  Чтобы воспользоваться пользовательским компонентом преобразования вместо C# можно также использовать JavaScript, Visual Basic или C++.  
  
 В большинстве случаев можно использовать C + +/ CX для создания среды выполнения Windows). Тем не менее иногда необходимо использовать WRL. Например при создании медиа-расширения для Microsoft Media Foundation, необходимо создать компонент, реализующий интерфейсы COM и среды выполнения Windows. Поскольку C + +/ CX можно создавать только объекты среды выполнения Windows, для создания медиа-расширения необходимо использовать WRL, так как она позволяет реализовывать интерфейсы COM и среды выполнения Windows.  

> [!NOTE]
>  Хотя этот пример кода является объемным, он показывает минимум, необходимый для создания полезных преобразований Media Foundation. Его можно использовать в качестве отправной точки для собственного пользовательского преобразования. Этот пример взят из [примера медиарасширений](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096), медиарасширения для применения эффектов к видео, декодирования видео и создания обработчиков схем, производящих медиапотоки.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Благодаря [среды выполнения Windows](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   опыт работы с моделью COM;  
  
-   веб-камера.  
  
## <a name="key-points"></a>Ключевые моменты  
  
-   Для создания пользовательского компонента Media Foundation используйте файл определения языка MIDL, чтобы определить и реализовать интерфейс, а затем сделать его активируемым из других компонентов.  
  
-   `namespace` И `runtimeclass` атрибуты и `NTDDI_WIN8` [версии](http://msdn.microsoft.com/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81) значения атрибута являются важными частями определения компонента Media Foundation, который использует WRL на языке MIDL.  
  
-   [Microsoft::wrl:: runtimeclass](../windows/runtimeclass-class.md) является базовым классом для пользовательского компонента Media Foundation. [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](../windows/runtimeclasstype-enumeration.md) значение перечисления, который предоставляется как аргумент шаблона, помечает класс для использования и как класс среды выполнения Windows и как классического COM-класса среды выполнения.  
  
-   [InspectableClass](../windows/inspectableclass-macro.md) макрос реализует базовую функциональность модели COM, такую как подсчет ссылок и `QueryInterface` метод и задает имя класса среды выполнения и уровень доверия.  
  
-   Использовать Microsoft::WRL::[класс модуля](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe) для реализации функций DLL точки входа, такие как [DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx), и [ DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx).  
  
-   Необходимо установить связь между компонентом DLL и runtimeobject.lib. Также укажите [/WINMD](../cppcx/compiler-and-linker-options-c-cx.md) в строке компоновщика для создания метаданных Windows.  
  
-   Использование ссылок на проекты благодаря компонентов WRL становится доступной для приложений универсальной платформы Windows.  
  
### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Использовать компонент изменять WRL для создания в оттенках серого Media Foundation  
  
1.  В Visual Studio создайте **пустое решение** проекта. Например, назовите проект, *MediaCapture*.  
  
2.  Добавить **DLL (универсальные Windows)** проекта к решению. Например, назовите проект, *GrayscaleTransform*.  
  
3.  Добавить **файл Midl (.idl)** файл в проект. Имя файла, например, *GrayscaleTransform.idl*.  
  
4.  Добавьте в файл GrayscaleTransform.idl следующий код:  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  Используйте указанный ниже код, чтобы заменить содержимое `pch.h`.  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  Добавьте в проект новый файл заголовка, назовите его `BufferLock.h`, а затем добавьте следующий код:  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  `GrayscaleTransform.h` в этом примере не используется. Его можно удалить из проекта при необходимости.  
  
8.  Используйте указанный ниже код, чтобы заменить содержимое `GrayscaleTransform.cpp`.  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. Добавьте в проект новый файл определения модуля, назовите его `GrayscaleTransform.def`, а затем добавьте следующий код:  
  
   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```   
  
10. Используйте указанный ниже код, чтобы заменить содержимое `dllmain.cpp`.  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. В проекте **страницы свойств** диалоговом окне установите следующие **компоновщика** свойства.  
  
    1.  В разделе **ввода**, для **файл определения модуля**, укажите `GrayScaleTransform.def`.  
  
    2.  Также в разделе **ввода**, добавьте `runtimeobject.lib`, `mfuuid.lib`, и `mfplatf.lib` для **Дополнительные зависимости** свойство.  
  
    3.  В разделе **метаданных Windows**, задайте **создавать метаданные Windows** для **Да (/ WINMD)**.  
  
### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Использование пользовательского компонента Media Foundation из приложения C# WRL  
  
1.  Добавьте новый **C# пустое приложение (XAML)** проект `MediaCapture` решения. Например, назовите проект, *MediaCapture*.  
  
2.  В **MediaCapture** проекта, добавьте ссылку на `GrayscaleTransform` проекта. Чтобы узнать как это сделать, см. в разделе [как: Добавление и удаление ссылок с помощью диспетчера ссылок](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).  
  
3.  В `Package.appxmanifest`на **возможности** выберите **"микрофон"** и **веб-камера**. Обе возможности необходимы для получения фотографий с веб-камеры.  
  
4.  В `MainPage.xaml`, добавьте следующий код к корню [сетки](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) элемент:  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  Используйте указанный ниже код, чтобы заменить содержимое `MainPage.xaml.cs`.  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 На следующем рисунке показано `MediaCapture app`.  
  
 ![Приложение mediacapture, захватывающее фотографию](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>Следующие шаги  
 Пример показывает способ записи фотографий (по одной) с веб-камеры по умолчанию. [Пример расширений мультимедиа](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) делает больше. В нем показано, как выполнить перебор веб-камер и работать с локальными обработчиками схем, а также демонстрируются дополнительные медиа-эффекты, работающие как на отдельных фотографиях, так и на потоках видео.  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [Пример расширений мультимедиа](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)