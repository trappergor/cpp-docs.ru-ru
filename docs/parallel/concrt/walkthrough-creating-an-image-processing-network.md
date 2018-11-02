---
title: Пошаговое руководство. Создание сети обработки изображений
ms.date: 11/04/2016
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 4eb1d6f9e5bc0055a1a4b4be5e18497b20c3a73a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643642"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>Пошаговое руководство. Создание сети обработки изображений

В этом документе показано, как создавать сеть асинхронных блоков сообщений, выполняющих обработку изображений.

Сети определяет, какие операции выполнять на изображении, в зависимости от свойств. В этом примере используется *потока данных* модели для перемещения изображений по сети. В модели потока данных независимые компоненты программы взаимодействуют друг с другом, отправляя сообщения. Когда компонент получает сообщение, он выполнения некоторых операций и затем передать результат этого действия другому компоненту. Сравните это с *поток управления* модели, в который приложение использует структуры управления, например, условные операторы, циклы и т. д., для управления порядком операций в программе.

Сети, которая зависит от потока данных создает *конвейера* задач. Каждый этап конвейера параллельно выполняет часть общей задачи. Можно сравнить это с линией сборки автомобилей. Как при продвижении автомобиля по сборочной линии, одна станция собирает раму, другая — устанавливает двигатель и т. д. Включив можно собирать одновременно много автомобилей, линия сборки обеспечивает большую производительность, чем полная сборка автомобилей одной за раз.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступать к этому руководству, приведены в следующих источниках:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [Пошаговое руководство. Создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Также рекомендуется разобраться в основах GDI +, прежде чем приступать к этому руководству.

##  <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Определение функции обработки изображений](#functionality)

- [Создание сети обработки изображений](#network)

- [Полный пример](#complete)

##  <a name="functionality"></a> Определение функции обработки изображений

В этом разделе представлены функции поддержки, которые использует сеть обработки изображений для работы с образами, которые считываются с диска.

Следующие функции, `GetRGB` и `MakeColor`, извлекают и объединяют отдельные компоненты данного цвета, соответственно.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Следующая функция, `ProcessImage`, вызовы данного [std::function](../../standard-library/function-class.md) объекта для преобразования значения цвет каждого пикселя в GDI + [точечного рисунка](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) объекта. `ProcessImage` Функция использует [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм для обработки каждой строки точечного рисунка в параллельном режиме.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

Следующие функции, `Grayscale`, `Sepiatone`, `ColorMask`, и `Darken`, вызовите `ProcessImage` функция для преобразования значения цвет каждого пикселя `Bitmap` объекта. Каждая из этих функций использует лямбда-выражение для определения преобразования цвет одного пикселя.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Следующая функция `GetColorDominance`, также вызывает `ProcessImage` функции. Тем не менее, вместо того чтобы менять значение каждого цвета, эта функция использует [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) объекты для вычисления, превосходит ли компонент красного, зеленого или синего цвета изображения.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Следующая функция `GetEncoderClsid`, извлекает идентификатор класса для данного типа MIME кодировщика. Приложение использует эту функцию для получения кодировщик для растрового изображения.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[В начало](#top)]

##  <a name="network"></a> Создание сети обработки изображений

В этом разделе описывается, как создавать сеть асинхронных блоков сообщений, которые выполняют обработку изображений на каждое изображение JPEG (.jpg) в указанном каталоге. Сети выполняет следующие операции обработки изображений.

1. Все изображения, созданные пользователем Tom преобразование в оттенки серого.

1. Все изображения, красный базового цвета удалите зеленый и синий компоненты и затем затемнить его.

1. Для любого другого изображения примените тонирования выцветшей фотографии.

Сеть применяет только первой операции обработки изображений, соответствующий одному из этих условий. Например если изображение создано пользователем Tom и красный преобладающего цвета, изображение только преобразуется в оттенки серого.

После сети каждой операции обработки изображений, он сохраняет изображение на диск в формате точечного рисунка (BMP).

Ниже показано, как создать функцию, которая реализует этот образ, обработка сети и применяет эту сеть для каждого изображения в формате JPEG в указанном каталоге.

#### <a name="to-create-the-image-processing-network"></a>Создание сети обработки изображений

1. Создание функции, `ProcessImages`, который принимает имя папки на диске.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. В `ProcessImages` функцию, создайте `countdown_event` переменной. `countdown_event` Класс показан далее в этом пошаговом руководстве.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Создание [std::map](../../standard-library/map-class.md) объект, который связывает `Bitmap` объект с исходным именем файла.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Добавьте следующий код для определения элементов сети обработки изображений.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Добавьте следующий код для подключения к сети.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Добавьте следующий код, чтобы отправить в начало сети полный путь к каждой JPEG-файл в каталоге.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. Дождитесь `countdown_event` переменной достигнет нуля.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

Следующая таблица описывает члены сети.

|Член|Описание|
|------------|-----------------|
|`load_bitmap`|Объект [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) объект, который загружает `Bitmap` с диска и добавляет запись в `map` для связи с исходным именем файла изображения.|
|`loaded_bitmaps`|Объект [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объект, отправляющий загруженные изображения фильтрам обработки изображений.|
|`grayscale`|Объект `transformer` объект, выполняющий преобразование изображения, созданные пользователем Tom в оттенки серого. Он использует метаданные изображения, чтобы определить ее автора.|
|`colormask`|Объект `transformer` объект, который удаляет компоненты зеленого и синего цветов из изображений, красный основной цвет.|
|`darken`|Объект `transformer` , затемняющий изображения, в которых красный основной цвет.|
|`sepiatone`|Объект `transformer` объекта, к которому применяется выцветшей фотографии тонирования образы, не созданные пользователем Tom и не являющихся преобладает красный цвет.|
|`save_bitmap`|Объект `transformer` объект, который сохраняет обработанные `image` на диск как растровое изображение. `save_bitmap` Получает имя исходного файла из `map` объекта и изменяет расширение имени файла на BMP.|
|`delete_bitmap`|Объект `transformer` объект, который освобождает память для изображений.|
|`decrement`|Объект [concurrency::call](../../parallel/concrt/reference/call-class.md) объект, действующий как конечный узел в сети. Он уменьшает `countdown_event` чтобы сообщить главному приложению, что образ был обработан.|

`loaded_bitmaps` Буфер сообщений важна, поскольку как `unbounded_buffer` объекта, он предлагает `Bitmap` объектов между несколькими получателями. Если целевой блок принимает `Bitmap` объекта, `unbounded_buffer` объекта не предлагает этот `Bitmap` объекта к другим целевым объектам. Таким образом, порядок, в котором вы свяжете объектов `unbounded_buffer` важен. `grayscale`, `colormask`, И `sepiatone` блоки использовать фильтр, чтобы принимать сообщения только определенные `Bitmap` объектов. `decrement` Буфер сообщений является важным цель `loaded_bitmaps` буфера сообщений, так как он принимает все `Bitmap` объекты, которые будут отклонены буферов сообщений. `unbounded_buffer` Объект обязательно должен передавать сообщения в порядке. Таким образом `unbounded_buffer` объект блокирует до новой целевой блок, связанного с ним и принимает сообщение, если нет текущей целевой блок не примет это сообщение.

Если приложение требует, что сообщение обрабатывалось несколькими блоками сообщений, а только одним блоком, сначала принимает сообщение, можно использовать другой тип блока сообщений, таких как `overwrite_buffer`. `overwrite_buffer` Класс содержит одно сообщение за раз, но он формирует и передает это сообщение на каждый из его целевых объектов.

На следующем рисунке показан сеть обработки изображений:

![Сеть обработки изображений](../../parallel/concrt/media/concrt_imageproc.png "concrt_imageproc")

`countdown_event` Объект в этом примере включает сеть обработки изображений для информирования основного приложения, когда будут обработаны все образы. `countdown_event` Класс использует [concurrency::event](../../parallel/concrt/reference/event-class.md) объекта, чтобы сообщить, что значение счетчика достигло нуля. Основное приложение увеличивает значение счетчика, каждый раз, что он отправляет имя файла в сети. Конечный узел сети уменьшает счетчик после обработки каждого изображения. После основного приложения проходит через указанный каталог, он ожидает `countdown_event` чтобы сообщить, что его счетчика равно нулю.

В следующем примере показан `countdown_event` класса:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[В начало](#top)]

##  <a name="complete"></a> Полный пример

Ниже приведен полный пример кода. `wmain` Функция управляет GDI + библиотеку и вызывает `ProcessImages` функции для обработки JPEG файлы в `Sample Pictures` каталога.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

Ниже показан пример выходных данных. Исходные изображения расположены над соответствующими измененными изображениями.

![Пример выходных данных для примера](../../parallel/concrt/media/concrt_imageout.png "concrt_imageout")

`Lighthouse` созданные пользователем Tom Alphin и таким образом, преобразуется в оттенки серого. `Chrysanthemum`, `Desert`, `Koala`, и `Tulips` красный базового цвета и таким образом быть удалены компоненты сине-зеленый цвет и затемняются. `Hydrangeas`, `Jellyfish`, и `Penguins` соответствующие критериям по умолчанию и, следовательно, сепия toned.

[[В начало](#top)]

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `image-processing-network.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe /DUNICODE/EHsc/Link изображение processing-network.cpp gdiplus.lib**

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
