---
title: Пошаговое руководство. Создание приложения UWP с использованием WRL и Media Foundation
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: 272092982c5e9cc57f52043e08c8bd384c43ea96
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031515"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Пошаговое руководство. Создание приложения UWP с использованием WRL и Media Foundation

> [!NOTE]
> Для новых приложений и компонентов UWP мы рекомендуем [использовать](/windows/uwp/cpp-and-winrt-apis/)новую стандартную языковую проекцию на язык с Индексом Азино в течение 17 лет для AI-аДО для Windows Runtime. СИ/Винрт доступен в Windows 10 SDK начиная с версии 1803 года. СИ/Винрт полностью реализован в файлах заголовков и предназначен для предоставления вам первоклассного доступа к современному API Windows.

В этом уроке вы узнаете, как использовать библиотеку шаблонов Windows Runtime C 'Template Library (WRL) для создания универсального приложения платформы Windows (UWP), использующее [Microsoft Media Foundation.](/windows/win32/medfound/microsoft-media-foundation-sdk)

В этом примере создается пользовательский объект Media Foundation, который применяет эффект "оттенки серого" к изображениям, полученным с веб-камеры. Приложение использует C++ для определения пользовательского преобразования и C# для использования компонента и выполнения преобразования захваченного изображения.

> [!NOTE]
> Чтобы воспользоваться пользовательским компонентом преобразования вместо C# можно также использовать JavaScript, Visual Basic или C++.

В большинстве случаев для создания Windows Runtime можно использовать C-CX. Тем не менее, иногда вы должны использовать WRL. Например, при создании медиа-расширения для Microsoft Media Foundation необходимо создать компонент, который реализует интерфейсы COM и Windows Runtime. Поскольку C-CX может создавать только объекты Windows Runtime, для создания расширения мультимедиа необходимо использовать WRL, поскольку он позволяет реализовать интерфейсы COM и Windows Runtime.

> [!NOTE]
> Хотя этот пример кода является объемным, он показывает минимум, необходимый для создания полезных преобразований Media Foundation. Его можно использовать в качестве отправной точки для собственного пользовательского преобразования. Этот пример адаптирован из [образца расширений мультимедиа,](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)который использует расширения мультимедиа для применения эффектов к видео, декодирования видео и создания обработчиков схем, которые производят потоки мультимедиа.

## <a name="prerequisites"></a>Предварительные требования

- В Visual Studio 2017 и позже поддержка UWP является дополнительным компонентом. Чтобы установить его, откройте Visual Studio Installer из меню Windows Start и найдите свою версию Visual Studio. Выберите **«Изменить»,** а затем убедитесь, что плитка **универсальной платформы Windows** проверяется. В рамках **проверки дополнительных компонентов** **инструменты Для UWP (v141)** для Visual Studio 2017, или **инструменты C» для UWP (v142)** для Visual Studio 2019. Затем проверьте версию Windows SDK, которую вы хотите использовать.

- Опыт работы с [Windows Runtime](/uwp/api/).

- опыт работы с моделью COM;

- Веб-камера,

## <a name="key-points"></a>Ключевые моменты

- Для создания пользовательского компонента Media Foundation используйте файл определения языка MIDL, чтобы определить и реализовать интерфейс, а затем сделать его активируемым из других компонентов.

- Значение `namespace` `runtimeclass` атрибутов и `NTDDI_WIN8`атрибутов [версии](/windows/win32/Midl/version) являются важными частями определения MIDL для компонента Media Foundation, использующем WRL.

- [Microsoft::WRL::RuntimeClass](runtimeclass-class.md) является базовым классом для пользовательского компонента Media Foundation. [Значение значения Microsoft:::WRL::RuntimeClassType::WinRtClassicComMix,](runtimeclasstype-enumeration.md) которое представлено в качестве аргумента шаблона, обозначит класс для использования как в качестве класса Runtime Windows, так и в качестве классического класса выполнения COM.

- Макрос [InspectableClass](inspectableclass-macro.md) реализует основные функциональные возможности `QueryInterface` COM, такие как подсчет ссылок и метод, и устанавливает имя и уровень доверия класса выполнения.

- Используйте Microsoft::WRL::[Класс модуля](module-class.md) для реализации функций DLL начальной точки, таких как [DllGetActivationFactory,](/windows/win32/winrt/functions) [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)и [DllGetClassObject.](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)

- Необходимо установить связь между компонентом DLL и runtimeobject.lib. Также укажите [/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md) на линии ссылки для генерации метаданных Windows.

- Используйте ссылки на проекты, чтобы сделать компоненты WRL доступными для приложений UWP.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Использовать WRL для создания компонента преобразования серого масштаба Media Foundation

1. В Visual Studio создайте проект **«Пустое решение».** Назовите проект, например, *MediaCapture*.

1. Добавьте в решение проект **DLL (Universal Windows).** Назовите проект, например, *GrayscaleTransform*.

1. Добавьте в проект файл **Midl File (.idl).** Назовите файл, например, *GrayscaleTransform.idl*.

1. Добавьте этот код в GrayscaleTransform.idl:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. Используйте следующий код для `pch.h`замены содержимого:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Добавьте новый файл заголовка в `BufferLock.h`проект, назовите его, а затем замените содержимое этим кодом:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`не используется в этом примере. Его можно удалить из проекта при необходимости.

1. Используйте следующий код для `GrayscaleTransform.cpp`замены содержимого:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Добавьте в проект новый файл определения `GrayscaleTransform.def`модуля, назовите его, а затем добавьте этот код:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. Используйте следующий код для `dllmain.cpp`замены содержимого:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. В диалоговом окне **страниц свойств** проекта установите следующие свойства **Linker.**

   1. Под **входного ,** для **файла определения модуля**, укажите `GrayScaleTransform.def`.

   1. Также под **вход,** `runtimeobject.lib` `mfuuid.lib`добавить `mfplat.lib` , , и **дополнительные зависимости собственности.**

   1. Под **метаданными Windows,** набор **Генерировать Windows Метаданные** да **(/WINMD)**.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Использовать WRL пользовательский компонент Media Foundation из приложения C

1. Добавьте к решению `MediaCapture` новый проект **«Бланк-Бланк» (Universal Windows).** Назовите проект, например, *MediaCapture*.

1. В проекте **MediaCapture** добавьте `GrayscaleTransform` ссылку на проект. Чтобы узнать, как: [Добавить или удалить ссылки с помощью справочного менеджера](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. В `Package.appxmanifest`, на вкладке **Возможности,** выберите **Микрофон** и **веб-камера**. Обе возможности необходимы для получения фотографий с веб-камеры.

1. В, `MainPage.xaml`добавьте этот код к элементу [корневой сетки:](/uwp/api/windows.ui.xaml.controls.grid)

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. Используйте следующий код для `MainPage.xaml.cs`замены содержимого:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

Следующая иллюстрация `MediaCapture app`показывает .

![Приложение MediaCapture, захватывающее фотографию](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Next Steps

Пример показывает способ записи фотографий (по одной) с веб-камеры по умолчанию. [Образец расширений мультимедиа](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) делает больше. В нем показано, как выполнить перебор веб-камер и работать с локальными обработчиками схем, а также демонстрируются дополнительные медиа-эффекты, работающие как на отдельных фотографиях, так и на потоках видео.

## <a name="see-also"></a>См. также раздел

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Фонд Microsoft Media](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[Образец расширения мультимедиа](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
