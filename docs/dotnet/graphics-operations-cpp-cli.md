---
title: Работа с графикой (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: dd27fc603454d18f30fb367399e0ee18be74015e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505434"
---
# <a name="graphics-operations-ccli"></a>Работа с графикой (C++/CLI)

В этом разделе демонстрируется обработка изображений с помощью пакета SDK для Windows.

В следующих разделах описывается использование <xref:System.Drawing.Image?displayProperty=fullName> классом для выполнения обработки изображений.

## <a name="display"></a> Отображение изображений в платформе .NET Framework

В следующем примере кода изменяется для получения указателя на обработчик событий OnPaint <xref:System.Drawing.Graphics> объект главной формы. <xref:System.Windows.Forms.Form.OnPaint%2A> Функция предназначена для приложения Windows Forms, скорее всего, созданные с помощью мастера приложений Visual Studio.

Образ представлен <xref:System.Drawing.Image> класса. Данные изображения загружается из файла .jpg, с помощью <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> метод. Перед началом рисования изображения в форму, размер формы изменяется в соответствии с изображением. Рисование изображения выполняется с помощью <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> метод.

<xref:System.Drawing.Graphics> И <xref:System.Drawing.Image> классы находятся в <xref:System.Drawing?displayProperty=fullName> пространства имен.

### <a name="example"></a>Пример

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override
{
    Graphics^ g = pe->Graphics;
    Image^ image = Image::FromFile("SampleImage.jpg");
    Form::ClientSize = image->Size;
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );
}
```

## <a name="draw"></a> Рисование фигур при помощи .NET Framework

В следующем примере кода используется <xref:System.Drawing.Graphics> класс для изменения <xref:System.Windows.Forms.Form.OnPaint%2A> обработчик событий для получения указателя на <xref:System.Drawing.Graphics> объект главной формы. Этот указатель используется для задать цвет фона формы и рисования линии и дуги с помощью <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> и <xref:System.Drawing.Graphics.DrawArc%2A> методы.

### <a name="example"></a>Пример

```cpp
#using <system.drawing.dll>
using namespace System;
using namespace System::Drawing;
// ...
protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override
{
   Graphics^ g = pe->Graphics;
   g->Clear(Color::AntiqueWhite);

   Rectangle rect = Form::ClientRectangle;
   Rectangle smallRect;
   smallRect.X = rect.X + rect.Width / 4;
   smallRect.Y = rect.Y + rect.Height / 4;
   smallRect.Width = rect.Width / 2;
   smallRect.Height = rect.Height / 2;

   Pen^ redPen = gcnew Pen(Color::Red);
   redPen->Width = 4;
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);

   Pen^ bluePen = gcnew Pen(Color::Blue);
   bluePen->Width = 10;
   g->DrawArc( bluePen, smallRect, 90, 270 );
}
```

## <a name="rotate"></a> Поворот изображений с помощью .NET Framework

В следующем примере кода демонстрируется использование <xref:System.Drawing.Image?displayProperty=fullName> класс для загрузки изображения с диска, повернуть на 90 градусов и сохраните его как новый файл .jpg.

### <a name="example"></a>Пример

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );
   image->Save("SampleImage_rotated.jpg");
   return 0;
}
```

## <a name="convert"></a> Преобразование форматов файлов изображений в .NET Framework

В следующем примере кода показано <xref:System.Drawing.Image?displayProperty=fullName> класс и <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> перечисление, используемое для преобразования и сохранять файлы изображений. Следующий код загружает изображение из JPG-файлу и сохраняет его в форматах GIF и BMP.

### <a name="example"></a>Пример

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->Save("SampleImage.png", ImageFormat::Png);
   image->Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}
```

## <a name="related-sections"></a>Связанные разделы

[Приступая к программированию графики](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[Управляемый код GDI+](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>См. также

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
