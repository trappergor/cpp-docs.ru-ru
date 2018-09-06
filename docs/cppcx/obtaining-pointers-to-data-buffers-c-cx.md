---
title: Получение указателей на буферы данных (C + +/ CX) | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: db4f9370-dd95-4896-b5b8-4b202284f579
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8a36573e72b173180e89b48403829a9387d4ee8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757027"
---
# <a name="obtaining-pointers-to-data-buffers-ccx"></a>Получение указателей на буферы данных (C++/CX)
В среде выполнения Windows [Windows::Storage::Streams::IBuffer](https://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ibuffer.aspx) интерфейс предоставляет не зависящий от языка и основанный способ доступа к буферам данных. В C++ можно получить необработанный указатель на базовый массив байтов с помощью интерфейса IBufferByteAccess библиотеки среды выполнения Windows, определенный в файле robuffer.h. Благодаря такому подходу можно изменить массив байтов на месте без создания лишний копий данных.  
  
 В примере ниже показан элемент изображения XAML, источником которого является [Windows::UI::Xaml::Media::Imaging WriteableBitmap](https://msdn.microsoft.com/%20library/windows/apps/windows.ui.xaml.media.imaging.writeablebitmap.aspx). Клиентские приложения, написанные на любом языке, могут передавать ссылку на `WriteableBitmap` в код C++, а затем код C++ может использовать эту ссылку для обращения к соответствующему буферу. В приложении универсальной платформы Windows, которое создается на языке C++ можно использовать функцию в следующем примере непосредственно в исходном коде без упаковки в компонент среды выполнения Windows.  
  
 ![C&#43; &#43; кодом, напрямую обращается к данным пикселя](../cppcx/media/ibufferbyteaccessdiagram.png "IBufferByteAccessDiagram")  
  
## <a name="getpointertopixeldata"></a>GetPointerToPixelData  
 Следующий метод принимает [Windows::Storage::Streams::IBuffer](https://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ibuffer.aspx) и возвращает необработанный указатель на соответствующий массив байтов. Чтобы вызвать функцию, передайте [WriteableBitmap::PixelBuffer](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.media.imaging.writeablebitmap.pixelbuffer.aspx) свойство.  
  
```  
  
#include <wrl.h>  
#include <robuffer.h>  
using namespace Windows::Storage::Streams;  
using namespace Microsoft::WRL;  
typedef uint8 byte;  
// Retrieves the raw pixel data from the provided IBuffer object.  
// Warning: The lifetime of the returned buffer is controlled by  
// the lifetime of the buffer object that's passed to this method.  
// When the buffer has been released, the pointer becomes invalid  
// and must not be used.  
byte* Class1::GetPointerToPixelData(IBuffer^ pixelBuffer, unsigned int *length)  
{  
    if (length != nullptr)  
    {  
        *length = pixelBuffer ->Length;  
    }  
    // Query the IBufferByteAccess interface.  
    ComPtr<IBufferByteAccess> bufferByteAccess;  
    reinterpret_cast<IInspectable*>( pixelBuffer)->QueryInterface(IID_PPV_ARGS(&bufferByteAccess));  
  
    // Retrieve the buffer data.  
    byte* pixels = nullptr;  
    bufferByteAccess->Buffer(&pixels);  
    return pixels;  
}  
```  
  
## <a name="complete-example"></a>Полный пример  
 Ниже показано, как создать приложение C# универсальной Windows платформы, который передает `WriteableBitmap` в библиотеку DLL компонента среды выполнения Windows на C++. Код C++ получает указатель на буфер пикселя, выполняющий простое изменение изображения на месте. В качестве альтернативы можно создать клиентское приложение на языке Visual Basic, JavaScript или C++, а не на C#. При использовании C++ нет необходимости в компоненте DLL; можно просто добавить эти методы непосредственно в класс MainPage или в какие-либо другие классы.  
  
#### <a name="create-the-client"></a>Создание клиента  
  
1.  Используйте шаблон проекта пустого приложения для создания приложения C# универсальной Windows платформы.  
  
2.  В файле MainPage.xaml  
  
    -   Используйте это XAML-файл, чтобы заменить элемент `Grid` :  
  
        ```cpp  
        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">  
                <StackPanel HorizontalAlignment="Left" Margin="176,110,0,0" VerticalAlignment="Top" Width="932">  
                    <Image x:Name="Pic"/>  
                    <Button Content="Process Image" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Height="47" Click="Button_Click_1"/>  
                </StackPanel>  
            </Grid>  
        ```  
  
3.  В файле MainPage.xaml.cs  
  
    1.  Добавьте следующие объявления пространств имен:  
  
        ```  
        using Windows.Storage;  
        using Windows.Storage.FileProperties;  
        using Windows.UI.Xaml.Media.Imaging;  
        using Windows.Storage.Streams;  
        using Windows.Storage.Pickers;  
        ```  
  
    2.  Добавьте переменную-член `WriteableBitmap` в класс `MainPage` и присвойте ей имя `m_bm`.  
  
        ```  
        private WriteableBitmap m_bm;  
        ```  
  
    3.  С помощью следующего кода замените заглушку метода `OnNavigatedTo` . В результате при запуске приложения будет открываться средство выбора файлов. (Обратите внимание, что в сигнатуру функции добавляется ключевое слово `async` ).  
  
        ```c#  
        async protected override void OnNavigatedTo(NavigationEventArgs e)  
                {  
                    FileOpenPicker openPicker = new FileOpenPicker();  
                    openPicker.ViewMode = PickerViewMode.Thumbnail;  
                    openPicker.SuggestedStartLocation = PickerLocationId.PicturesLibrary;  
                    openPicker.FileTypeFilter.Add(".jpg");  
                    openPicker.FileTypeFilter.Add(".jpeg");  
                    openPicker.FileTypeFilter.Add(".png");  
  
                    StorageFile file = await openPicker.PickSingleFileAsync();  
                    if (file != null)  
                    {  
                        // Get the size of the image for the WriteableBitmap constructor.  
                        ImageProperties props = await file.Properties.GetImagePropertiesAsync();  
                        m_bm = new WriteableBitmap((int)props.Height, (int)props.Width);  
                        m_bm.SetSource(await file.OpenReadAsync());  
                        Pic.Source = m_bm;  
                    }  
                    else  
                    {  
                      //  Handle error...  
                    }  
                }  
        ```  
  
    4.  Добавьте обработчик событий для нажатия кнопки. (Так как ссылка на пространство имен `ImageManipCPP` еще не создана, он может быть подчеркнут волнистой линией в окне редактора).  
  
        ```  
        async private void Button_Click_1(object sender, RoutedEventArgs e)  
                {  
                    ImageManipCPP.Class1 obj = new ImageManipCPP.Class1();  
                    await obj.Negativize(m_bm);  
                    Pic.Source = m_bm;  
                }  
        ```  
  
#### <a name="create-the-c-component"></a>Создание компонента C++  
  
1.  Добавьте новый компонент среды выполнения Windows на C++ в существующее решение и назовите его `ImageManipCPP`. Добавьте ссылку на него в проект C#, щелкнув этот проект правой кнопкой мыши в **Обозревателе решений** и выбрав **Добавить**, **Ссылка**.  
  
2.  В файле Class1.h  
  
    1.  Добавьте определение `typedef` во вторую строку сразу после `#pragma once`.  
  
        ```  
        typedef uint8 byte;  
  
        ```  
  
    2.  Добавьте атрибут `WebHostHidden` перед началом объявления `Class1` .  
  
        ```  
        [Windows::Foundation::Metadata::WebHostHidden]  
        ```  
  
    3.  Добавьте следующую сигнатуру открытого метода в `Class1`:  
  
        ```  
        Windows::Foundation::IAsyncAction^ Negativize(Windows::UI::Xaml::Media::Imaging::WriteableBitmap^ bm);  
        ```  
  
    4.  Добавьте сигнатуру из метода `GetPointerToPixelData` , показанного в предыдущем фрагменте кода. Убедитесь, что этот метод является закрытым.  
  
3.  В файле Class1.cpp  
  
    1.  Добавьте следующие директивы `#include` и объявления пространств имен:  
  
        ```  
  
        #include <ppltasks.h>  
        #include <wrl.h>  
        #include <robuffer.h>  
  
        using namespace Windows::Storage;  
        using namespace Windows::UI::Xaml::Media::Imaging;  
        using namespace Windows::Storage::Streams;  
        using namespace Microsoft::WRL;  
  
        ```  
  
    2.  Добавьте реализацию `GetPointerToPixelData` из расположенного выше фрагмента кода.  
  
    3.  Добавьте реализацию `Negativize`. Этот метод создает эффект, похожий на фотонегатив, инвертируя каждое RGB-значение пикселя. Этот метод сделан асинхронным, поскольку на больших изображениях его выполнение может занять много времени.  
  
        ```  
        IAsyncAction^ Class1::Negativize(WriteableBitmap^ bm)  
        {  
            unsigned int length;  
            byte* sourcePixels = GetPointerToPixelData(bm->PixelBuffer, &length);  
            const unsigned int width = bm->PixelWidth;  
            const unsigned int height = bm->PixelHeight;  
  
            return create_async([this, width, height, sourcePixels]  
            {          
                byte* temp = sourcePixels;  
                for(unsigned int k = 0; k < height; k++)  
                {          
                    for (unsigned int i = 0; i < (width * 4); i += 4)  
                    {  
                        int pos = k * (width * 4) + (i);  
                        temp[pos] = ~temp[pos];  
                        temp[pos + 1] = ~temp[pos + 1] / 3;  
                        temp[pos + 2] = ~temp[pos + 2] / 2;  
                        temp[pos + 3] = ~temp[pos + 3];  
                    }  
                }  
            });  
  
        }  
        ```  
  
        > [!NOTE]
        >  Этот метод может выполняться быстрее, если для параллелизации операции используется AMP или библиотека параллельных шаблонов.  
  
4.  Убедитесь, что в папке рисунков есть по крайней мере одно изображение, а затем нажмите клавишу F5, чтобы компилировать и выполнить программу.