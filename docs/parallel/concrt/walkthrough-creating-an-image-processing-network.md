---
title: Пошаговое руководство. Создание сети обработки изображений
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 680037e0e14c3ebd9171cacf477520e025eecebe
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "69512163"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>Пошаговое руководство. Создание сети обработки изображений

В этом документе показано, как создать сеть асинхронных блоков сообщений, выполняющих обработку изображений.

Сеть определяет, какие операции должны выполняться с изображением на основе его характеристик. В этом примере модель *потока* данных используется для маршрутизации изображений по сети. В модели потока данных независимые компоненты программы взаимодействуют друг с другом, отправляя сообщения. Когда компонент получает сообщение, он может выполнить какое-либо действие и передать результат этого действия другому компоненту. Сравните это с моделью *потока управления* , в которой приложение использует структуры элементов управления, например условные операторы, циклы и т. д., для управления порядком операций в программе.

Сеть, основанная на потоке данных, создает *конвейер* задач. Каждый этап конвейера параллельно выполняет часть общей задачи. Можно сравнить это с линией сборки автомобилей. Так как каждый транспортный модуль проходит через строку сборки, одна станция выполняет сборку кадра, другой устанавливает подсистему и т. д. Разрешив одновременное сборку нескольких автомобилей, линия сборки обеспечивает лучшую пропускную способность по сравнению со сборкой полных транспортных средств по одному за раз.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, прочитайте следующие документы:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [Пошаговое руководство: Создание агента для обработки потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Также рекомендуется понимать основы интерфейса GDI+ перед началом работы с этим пошаговым руководством.

##  <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Определение функциональных возможностей обработки изображений](#functionality)

- [Создание сети обработки изображений](#network)

- [Полный пример](#complete)

##  <a name="functionality"></a>Определение функциональных возможностей обработки изображений

В этом разделе показаны функции поддержки, используемые сетью обработки изображений для работы с образами, которые считываются с диска.

Следующие функции, `GetRGB` и `MakeColor`, извлекают и объединяют отдельные компоненты заданного цвета соответственно.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Следующая функция `ProcessImage`,, вызывает заданный объект [std:: Function](../../standard-library/function-class.md) для преобразования значения цвета каждого пикселя в [растровом](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) объекте GDI+. Функция использует алгоритм [параллелизма::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) для параллельной обработки каждой строки точечного рисунка. `ProcessImage`

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

`Grayscale`Следующие функции, `Sepiatone`,, `Bitmap` и `Darken`вызывают функциюдляпреобразованиязначенияцветакаждогопикселявобъекте.`ProcessImage` `ColorMask` Каждая из этих функций использует лямбда-выражение для определения преобразования цвета одного пикселя.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Следующая функция `GetColorDominance`,, также `ProcessImage` вызывает функцию. Однако вместо изменения значения каждого цвета эта функция использует объекты [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) , чтобы вычислить, является ли изображение красным, зеленым или синим цветом частью изображения.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Следующая функция `GetEncoderClsid`возвращает идентификатор класса для заданного типа MIME кодировщика. Приложение использует эту функцию для получения кодировщика для точечного рисунка.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[В начало](#top)]

##  <a name="network"></a>Создание сети обработки изображений

В этом разделе описывается создание сети асинхронных блоков сообщений, выполняющих обработку изображений для каждого изображения JPEG (JPG) в заданном каталоге. Сеть выполняет следующие операции обработки образов:

1. Для любого образа, созданного Tom, преобразуйте его в градации серого.

1. Для любого изображения, которое имеет красный цвет в качестве главного, удалите зеленые и синие компоненты, а затем затемнить их.

1. Для любого другого образа примените выцветшей Тонинг.

Сеть применяет только первую операцию обработки изображения, которая соответствует одному из этих условий. Например, если изображение создано объектом Tom и имеет красный цвет в качестве главного, изображение преобразуется в градации серого.

После того как сеть выполняет каждую операцию обработки изображений, образ сохраняется на диск в виде файла точечного рисунка (BMP).

Ниже показано, как создать функцию, которая реализует эту сеть обработки изображений и применяет эту сеть к каждому изображению JPEG в указанном каталоге.

#### <a name="to-create-the-image-processing-network"></a>Создание сети обработки изображений

1. Создайте функцию `ProcessImages`, которая принимает имя каталога на диске.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. `ProcessImages` В функции `countdown_event` создайте переменную. `countdown_event` Класс показан далее в этом пошаговом руководстве.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Создайте объект [std:: Map](../../standard-library/map-class.md) , связывающий `Bitmap` объект с его исходным именем файла.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Добавьте следующий код, чтобы определить элементы сети обработки изображений.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Добавьте следующий код для подключения к сети.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Добавьте следующий код для отправки в заголовок сети полный путь к каждому файлу JPEG в каталоге.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. Дождитесь `countdown_event` , пока переменная достигнет нуля.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

Следующая таблица описывает члены сети.

|Член|Описание|
|------------|-----------------|
|`load_bitmap`|Объект [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) , который загружает `Bitmap` объект с диска и добавляет запись в `map` объект, чтобы связать изображение с его исходным именем файла.|
|`loaded_bitmaps`|Объект [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , который отправляет загруженные изображения в фильтры обработки изображений.|
|`grayscale`|`transformer` Объект, который преобразует изображения, созданные с помощью тома, в градации серого. Он использует метаданные образа для определения его автора.|
|`colormask`|`transformer` Объект, который удаляет зеленые и синие цветовые компоненты из изображений, которые имеют красный цвет в качестве главного.|
|`darken`|`transformer` Объект, который затемняет изображения с красным цветом в качестве главного.|
|`sepiatone`|`transformer` Объект, который применяет выцветшей Тонинг к изображениям, которые не созданы с помощью Tom и не являются преимущественно красными.|
|`save_bitmap`|Объект, сохраняющий обработанные `image` на диск в виде точечного рисунка. `transformer` `save_bitmap`Извлекает исходное имя файла из `map` объекта и изменяет расширение его имени на. bmp.|
|`delete_bitmap`|`transformer` Объект, освобождающий память для изображений.|
|`decrement`|Объект [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) , который выступает в качестве узла терминала в сети. Он уменьшает `countdown_event` объект, чтобы сообщить основному приложению о том, что изображение обработано.|

Буфер сообщений важен, так как в `unbounded_buffer` качестве объекта он предоставляет `Bitmap` объекты нескольким получателям. `loaded_bitmaps` Если целевой блок принимает `Bitmap` объект `unbounded_buffer` , объект не предоставляет этот `Bitmap` объект другим целевым объектам. Поэтому важен порядок, в котором объекты связываются с `unbounded_buffer` объектом. Блоки сообщений `colormask`, и `sepiatone` используют фильтр, чтобы принимать только определенные `Bitmap` объекты. `grayscale` Буфер сообщений является важной целью `loaded_bitmaps` буфера сообщений, так как он принимает все `Bitmap` объекты, отклоненные другими буферами сообщений. `decrement` `unbounded_buffer` Объект необходим для распространения сообщений по порядку. Таким образом, `unbounded_buffer` объект блокируется до тех пор, пока новый целевой блок не будет связан с ним и не примет сообщение, если текущий целевой блок не принимает это сообщение.

Если приложению требуется, чтобы несколько блоков сообщений обрабатывали сообщение, а не только один блок сообщений, который первым принимает сообщение, можно использовать другой тип блока сообщений, например `overwrite_buffer`. `overwrite_buffer` Класс содержит одно сообщение за раз, но оно распространяет это сообщение на все его цели.

На следующем рисунке показана сеть обработки изображений:

![Сеть обработки изображений](../../parallel/concrt/media/concrt_imageproc.png "Сеть обработки изображений")

`countdown_event` Объект в этом примере позволяет сети обработки изображений сообщать основному приложению о том, что все образы обработаны. Класс использует объект [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) , чтобы сообщить, что значение счетчика достигает нуля. `countdown_event` Основное приложение увеличивает счетчик каждый раз при отправке имени файла в сеть. Узел терминала сети уменьшает счетчик после обработки каждого образа. Когда основное приложение проходит по указанному каталогу, оно ждет, пока `countdown_event` объект сообщит, что его счетчик достиг нуля.

В следующем примере показан `countdown_event` класс:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[В начало](#top)]

##  <a name="complete"></a>Полный пример

Ниже приведен полный пример кода. Функция управляет библиотекой GDI+ и `ProcessImages` вызывает функцию для обработки JPEG файлов в `Sample Pictures` каталоге. `wmain`

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

На следующем рисунке показан пример выходных данных. Каждый исходный образ находится выше соответствующего измененного образа.

![Пример выходных данных для примера](../../parallel/concrt/media/concrt_imageout.png "Пример выходных данных для примера")

`Lighthouse`создается объектом Tom Алфин, поэтому он преобразуется в градации серого. `Chrysanthemum`, `Desert`, ,и`Tulips` имеют красный цвет, поэтому компоненты синего и зеленого цветов удаляются и затемнены. `Koala` `Hydrangeas`, `Jellyfish` и`Penguins` соответствуют критериям по умолчанию, поэтому выцветшей упрощенная.

[[В начало](#top)]

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `image-processing-network.cpp` , а затем выполните следующую команду в окне командной строки Visual Studio.

**CL. exe/ДУНИКОДЕ/EHsc имаже-процессинг-Нетворк. cpp/Link GDIPLUS. lib**

## <a name="see-also"></a>См. также

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
