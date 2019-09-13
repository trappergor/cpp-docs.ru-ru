---
title: Пошаговое руководство. Создание приложения UWP с использованием WRL и Media Foundation
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: ac2c16fb94646af7445d41010253967be126636a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498305"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Пошаговое руководство. Создание приложения UWP с использованием WRL и Media Foundation

> [!NOTE]
> Для новых приложений и компонентов UWP рекомендуется использовать [ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)— новую стандартную проекцию c++ 17 для Среда выполнения Windows API. C++/WinRT доступен в пакете SDK для Windows 10 из версии 1803. C++/WinRT реализован полностью в файлах заголовков и предназначен для предоставления доступа к современным API Windows через первый класс.

В этом руководстве вы узнаете, как использовать библиотеку шаблонов среда выполнения Windows C++ (WRL) для создания приложения универсальная платформа Windows (UWP), использующего [Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk).

В этом примере создается пользовательский объект Media Foundation, который применяет эффект "оттенки серого" к изображениям, полученным с веб-камеры. Приложение использует C++ для определения пользовательского преобразования и C# для использования компонента и выполнения преобразования захваченного изображения.

> [!NOTE]
> Чтобы воспользоваться пользовательским компонентом преобразования вместо C# можно также использовать JavaScript, Visual Basic или C++.

В большинстве случаев для создания среда выполнения Windows можно C++использовать/CX. Однако иногда необходимо использовать WRL. Например, при создании расширения мультимедиа для Microsoft Media Foundation необходимо создать компонент, реализующий интерфейсы COM и среда выполнения Windows. Поскольку C++в/CX можно создавать только объекты среда выполнения Windows, для создания расширения мультимедиа необходимо использовать WRL, так как он позволяет реализовать интерфейсы COM и среда выполнения Windows.

> [!NOTE]
> Хотя этот пример кода является объемным, он показывает минимум, необходимый для создания полезных преобразований Media Foundation. Его можно использовать в качестве отправной точки для собственного пользовательского преобразования. Этот пример адаптируется из [примера расширений мультимедиа](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096), в котором используются расширения мультимедиа для применения эффектов к видео, расшифровки видео и создания обработчиков схем, создающих потоки мультимедиа.

## <a name="prerequisites"></a>Предварительные требования

- В Visual Studio 2017 и более поздних версиях поддержка UWP является дополнительным компонентом. Чтобы установить его, откройте Visual Studio Installer из меню "Пуск" Windows и найдите свою версию Visual Studio. Выберите **изменить** и убедитесь, что выбран элемент **Разработка универсальная платформа Windows** . В разделе необязательные **компоненты** проверьте  **C++ средства для UWP (v141)** для Visual Studio 2017 или  **C++ Tools для UWP (v142)** для Visual Studio 2019. Затем проверьте версию Windows SDK, которую вы хотите использовать. 

- Опыт работы с [Среда выполнения Windows](/uwp/api/).

- опыт работы с моделью COM;

- веб-камера.

## <a name="key-points"></a>Ключевые моменты

- Для создания пользовательского компонента Media Foundation используйте файл определения языка MIDL, чтобы определить и реализовать интерфейс, а затем сделать его активируемым из других компонентов.

- Атрибуты `namespace` и `runtimeclass` , а также `NTDDI_WIN8`значение атрибута [Version](/windows/win32/Midl/version) являются важными частями определения MIDL для Media Foundation компонента, использующего WRL.

- [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md) является базовым классом для пользовательского компонента Media Foundation. Значение перечисления [Microsoft:: WRL:: RuntimeClassType:: WinRtClassicComMix](runtimeclasstype-enumeration.md) , которое указывается в качестве аргумента шаблона, помечает класс для использования в качестве класса среда выполнения Windows и классического класса среды выполнения COM.

- Макрос [InspectableClass](inspectableclass-macro.md) реализует базовые функциональные возможности com, такие как подсчет ссылок и `QueryInterface` метод, и задает имя класса среды выполнения и уровень доверия.

- Используйте класс Microsoft:: WRL::[module](module-class.md) , чтобы реализовать функции точки входа DLL, такие как [дллжетактиватионфактори](/windows/win32/winrt/functions), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)и [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject).

- Необходимо установить связь между компонентом DLL и runtimeobject.lib. Также укажите [/WinMD](../../cppcx/compiler-and-linker-options-c-cx.md) в строке компоновщика для создания метаданных Windows.

- Используйте ссылки проекта, чтобы сделать компоненты WRL доступными для приложений UWP.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Использование WRL для создания компонента преобразования в градациях серого Media Foundation

1. В Visual Studio создайте пустой проект **решения** . Присвойте проекту имя, например *медиакаптуре*.

1. Добавьте в решение проект **DLL (универсальный Windows)** . Присвойте проекту имя, например *грайскалетрансформ*.

1. Добавьте в проект файл **MIDL (. IDL)** . Присвойте файлу имя, например *грайскалетрансформ. idl*.

1. Добавьте следующий код в Грайскалетрансформ. IDL:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. Используйте следующий код, чтобы заменить содержимое `pch.h`:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Добавьте новый файл заголовка в проект, присвойте ему `BufferLock.h`имя, а затем замените содержимое следующим кодом:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`не используется в этом примере. Его можно удалить из проекта при необходимости.

1. Используйте следующий код, чтобы заменить содержимое `GrayscaleTransform.cpp`:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Добавьте новый файл определения модуля в проект, присвойте ему `GrayscaleTransform.def`имя, а затем добавьте следующий код:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. Используйте следующий код, чтобы заменить содержимое `dllmain.cpp`:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. В диалоговом окне **страницы свойств** проекта задайте следующие свойства компоновщика .

   1. В разделе **входные данные**для **файла определения модуля**укажите `GrayScaleTransform.def`.

   1. Кроме того, в разделе `runtimeobject.lib`входные данные `mfplat.lib` добавьте, `mfuuid.lib`и в свойство **Дополнительные зависимости** .

   1. В разделе **метаданные Windows**задайте для параметра **создать метаданные Windows** значение **Да (/WinMD)** .

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Использование WRL компонента пользовательского Media Foundation из C# приложения

1. Добавьте в `MediaCapture` решение новый  **C# проект пустого приложения (универсальное приложение Windows)** . Присвойте проекту имя, например *медиакаптуре*.

1. В проекте **медиакаптуре** добавьте ссылку на `GrayscaleTransform` проект. Дополнительные сведения см. в [разделе как Добавление и удаление ссылок с помощью диспетчера ссылок](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. В `Package.appxmanifest`на вкладке **возможности** выберите **микрофон** и **веб-камера**. Обе возможности необходимы для получения фотографий с веб-камеры.

1. В `MainPage.xaml`добавьте следующий код в корневой элемент [Grid](/uwp/api/Windows.UI.Xaml.Controls.Grid) :

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. Используйте следующий код, чтобы заменить содержимое `MainPage.xaml.cs`:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

На следующем рисунке показан `MediaCapture app`.

![Приложение медиакаптуре, записывающее фотографию](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Следующие шаги

Пример показывает способ записи фотографий (по одной) с веб-камеры по умолчанию. [Пример расширений мультимедиа](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) выполняет больше возможностей. В нем показано, как выполнить перебор веб-камер и работать с локальными обработчиками схем, а также демонстрируются дополнительные медиа-эффекты, работающие как на отдельных фотографиях, так и на потоках видео.

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk)<br/>
[Пример расширений мультимедиа](https://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)
