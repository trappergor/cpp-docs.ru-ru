---
title: Пошаговое руководство. Создание приложения универсальной платформы Windows, с использованием WRL и Media Foundation
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 28e8d4b2871dbd3bef0f30bae5480d346af50706
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558266"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Пошаговое руководство. Создание приложения универсальной платформы Windows, с использованием WRL и Media Foundation

> [!NOTE]
> Для новых приложений универсальной платформы Windows и компонентов, мы рекомендуем использовать [ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/), это новый C ++ 17 проекция стандартного для API среды выполнения Windows. C++/ WinRT доступна в пакете SDK для Windows 10 версии 1803 и далее. C++/ WinRT реализуется полностью в файлах заголовков и призвана предоставить вам доступ первого класса в современных API Windows.

В этом руководстве вы узнаете, как использовать среду выполнения Windows C++ библиотеки шаблонов (WRL) для создания приложения универсальной платформы Windows (UWP), которое использует [Microsoft Media Foundation](/windows/desktop/medfound/microsoft-media-foundation-sdk).

В этом примере создается пользовательский объект Media Foundation, который применяет эффект "оттенки серого" к изображениям, полученным с веб-камеры. Приложение использует C++ для определения пользовательского преобразования и C# для использования компонента и выполнения преобразования захваченного изображения.

> [!NOTE]
> Чтобы воспользоваться пользовательским компонентом преобразования вместо C# можно также использовать JavaScript, Visual Basic или C++.

В большинстве случаев можно использовать C++/CX для создания среды выполнения Windows. Тем не менее иногда необходимо использовать WRL. Например при создании медиа-расширения для Microsoft Media Foundation, необходимо создать компонент, реализующий интерфейсы COM и среды выполнения Windows. Так как C++/CX можно создавать только объекты среды выполнения Windows, для создания медиа-расширения необходимо использовать WRL, так как она позволяет реализовывать интерфейсы COM и среды выполнения Windows.

> [!NOTE]
> Хотя этот пример кода является объемным, он показывает минимум, необходимый для создания полезных преобразований Media Foundation. Его можно использовать в качестве отправной точки для собственного пользовательского преобразования. Этот пример взят из [примера медиарасширений](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096), медиарасширения для применения эффектов к видео, декодирования видео и создания обработчиков схем, производящих медиапотоки.

## <a name="prerequisites"></a>Предварительные требования

- В Visual Studio 2017 и более поздних версий поддержки универсальной платформы Windows является дополнительным компонентом. Чтобы установить его, откройте установщик Visual Studio в меню Windows Пуск и найдите вашей версии Visual Studio. Выберите **изменить** и убедитесь, что **разработка универсальной платформы Windows** проверяется плитки. В разделе **дополнительные компоненты** проверьте  **C++ средства для универсальной платформы Windows (версии 141)** для Visual Studio 2017 или  **C++ средства для универсальной платформы Windows (v142)** для Visual Studio 2019. Проверьте версию пакета SDK Windows, который вы хотите использовать. 

- Благодаря [среды выполнения Windows](https://msdn.microsoft.com/library/windows/apps/br211377.aspx).

- опыт работы с моделью COM;

- веб-камера.

## <a name="key-points"></a>Ключевые моменты

- Для создания пользовательского компонента Media Foundation используйте файл определения языка MIDL, чтобы определить и реализовать интерфейс, а затем сделать его активируемым из других компонентов.

- `namespace` И `runtimeclass` атрибуты и `NTDDI_WIN8` [версии](/windows/desktop/Midl/version) значения атрибута являются важными частями определения компонента Media Foundation, который использует WRL на языке MIDL.

- [Microsoft::wrl:: runtimeclass](runtimeclass-class.md) является базовым классом для пользовательского компонента Media Foundation. [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](runtimeclasstype-enumeration.md) значение перечисления, который предоставляется как аргумент шаблона, помечает класс для использования и как класс среды выполнения Windows и как классического COM-класса среды выполнения.

- [InspectableClass](inspectableclass-macro.md) макрос реализует базовую функциональность модели COM, такую как подсчет ссылок и `QueryInterface` метод и задает имя класса среды выполнения и уровень доверия.

- Использовать Microsoft::WRL::[класс модуля](module-class.md) для реализации функций DLL точки входа, такие как [DllGetActivationFactory](https://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](/windows/desktop/api/combaseapi/nf-combaseapi-dllcanunloadnow), и [ DllGetClassObject](/windows/desktop/api/combaseapi/nf-combaseapi-dllgetclassobject).

- Необходимо установить связь между компонентом DLL и runtimeobject.lib. Также укажите [/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md) в строке компоновщика для создания метаданных Windows.

- Использование ссылок на проекты благодаря компонентов WRL становится доступной для приложений универсальной платформы Windows.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Использовать компонент изменять WRL для создания в оттенках серого Media Foundation

1. В Visual Studio создайте **пустое решение** проекта. Например, назовите проект, *MediaCapture*.

1. Добавить **DLL (универсальные Windows)** проекта к решению. Например, назовите проект, *GrayscaleTransform*.

1. Добавить **файл Midl (.idl)** файл в проект. Имя файла, например, *GrayscaleTransform.idl*.

1. Добавьте GrayscaleTransform.idl следующий код:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. Используйте указанный ниже код, чтобы заменить содержимое `pch.h`:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Добавьте в проект новый файл заголовка, назовите его `BufferLock.h`, а затем замените содержимое следующим кодом:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h` не используется в этом примере. Его можно удалить из проекта при необходимости.

1. Используйте указанный ниже код, чтобы заменить содержимое `GrayscaleTransform.cpp`:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Добавьте в проект новый файл определения модуля, назовите его `GrayscaleTransform.def`, а затем добавьте следующий код:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. Используйте указанный ниже код, чтобы заменить содержимое `dllmain.cpp`:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. В проекте **страницы свойств** диалоговом окне установите следующие **компоновщика** свойства.

   1. В разделе **ввода**, для **файл определения модуля**, укажите `GrayScaleTransform.def`.

   1. Также в разделе **ввода**, добавьте `runtimeobject.lib`, `mfuuid.lib`, и `mfplat.lib` для **Дополнительные зависимости** свойство.

   1. В разделе **метаданных Windows**, задайте **создавать метаданные Windows** для **Да (/ WINMD)**.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Использование пользовательского компонента Media Foundation из приложения C# WRL

1. Добавьте новый **C# пустое приложение (универсальные Windows)** проект `MediaCapture` решения. Например, назовите проект, *MediaCapture*.

1. В **MediaCapture** проекта, добавьте ссылку на `GrayscaleTransform` проекта. Чтобы узнать как это сделать, см. в разделе [как: Добавление и удаление ссылок с помощью диспетчера ссылок](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. В `Package.appxmanifest`на **возможности** выберите **"микрофон"** и **веб-камера**. Обе возможности необходимы для получения фотографий с веб-камеры.

1. В `MainPage.xaml`, добавьте следующий код к корню [сетки](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) элемент:

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. Используйте указанный ниже код, чтобы заменить содержимое `MainPage.xaml.cs`:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

На следующем рисунке показано `MediaCapture app`.

![Приложение mediacapture, захватывающее фотографию](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Следующие шаги

Пример показывает способ записи фотографий (по одной) с веб-камеры по умолчанию. [Пример расширений мультимедиа](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) делает больше. В нем показано, как выполнить перебор веб-камер и работать с локальными обработчиками схем, а также демонстрируются дополнительные медиа-эффекты, работающие как на отдельных фотографиях, так и на потоках видео.

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/desktop/medfound/microsoft-media-foundation-sdk)<br/>
[Пример расширений мультимедиа](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)