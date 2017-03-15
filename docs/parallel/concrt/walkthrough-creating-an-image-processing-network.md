---
title: "Пошаговое руководство. Создание сети обработки изображений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "создание сетей преобразования изображений [среда выполнения с параллелизмом]"
  - "сети преобразования изображений, создание [среда выполнения с параллелизмом]"
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Пошаговое руководство. Создание сети обработки изображений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом документе показано, как создавать сеть асинхронных блоков сообщений, выполняющих обработку изображений.  
  
 В зависимости от свойств изображения сеть определяет, какие операции с ним необходимо выполнить.  В этом примере для перемещения изображений по сети используется модель *потока данных*.  В модели потока данных независимые компоненты программы взаимодействуют друг с другом посредством отправки сообщений.  Когда компонент получает сообщение, он может выполнить какое\-либо действие и передать результат этого действия другому компоненту.  Сравните эту модель с моделью *потока управления*, в которой приложение управляет действиями программы с помощью структур управления, например условных операторов, циклов и так далее.  
  
 Сеть, основанная на потоке данных, создает *конвейер* задач.  Каждый этап конвейера параллельно выполняет часть общей задачи.  Это можно сравнить с линией сборки автомобилей.  При продвижении автомобиля по линии сборки одна станция собирает раму, другая — устанавливает двигатель и так далее.  Так как при этом можно собирать одновременно много автомобилей, линия сборки обеспечивает большую производительность, чем полная сборка автомобилей по одному.  
  
## Обязательные компоненты  
 Прежде чем начать выполнение этого пошагового руководства, необходимо ознакомиться со следующими документами.  
  
-   [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
-   [Пошаговое руководство. Создание агента потоков данных](../Topic/Walkthrough:%20Creating%20a%20Dataflow%20Agent.md)  
  
 Также перед освоением этого пошагового руководства рекомендуется разобраться в основах [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  Дополнительные сведения о [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] см. в разделе [GDI\+](_gdiplus_GDI_start_cpp).  
  
##  <a name="top"></a> Подразделы  
 Это пошаговое руководство содержит следующие подразделы.  
  
-   [Определение функции обработки изображений](#functionality)  
  
-   [Создание сети обработки изображений](#network)  
  
-   [Полный код примера](#complete)  
  
##  <a name="functionality"></a> Определение функции обработки изображений  
 В этом разделе демонстрируются необходимые функции, которые сеть обработки изображений использует для работы с изображениями, считываемыми с диска.  
  
 Следующие функции, `GetRGB` и `MakeColor`, извлекают и объединяют, соответственно, отдельные компоненты данного цвета.  
  
 [!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_1.cpp)]  
  
 Следующая функция, `ProcessImage`, вызывает данный объект [std::function](../../standard-library/function-class.md), чтобы преобразовать значение цвета каждого пикселя в объект [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [Bitmap](https://msdn.microsoft.com/en-us/library/ms534420.aspx).  Функция `ProcessImage` использует алгоритм [concurrency::parallel\_for](../Topic/parallel_for%20Function.md), чтобы параллельно обрабатывать все ряды растрового изображения.  
  
 [!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_2.cpp)]  
  
 Следующие функции, `Grayscale`, `Sepiatone`, `ColorMask` и `Darken`, вызывают функцию `ProcessImage`, чтобы преобразовать значение цвета каждого пикселя в объект `Bitmap`.  Все перечисленные функции используют лямбда\-выражения, чтобы определить преобразование цвета одного пикселя.  
  
 [!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_3.cpp)]  
  
 Следующая функция, `GetColorDominance`, также вызывает функцию `ProcessImage`.  При этом она не изменяет значение каждого цвета, а использует объекты [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), чтобы вычислить, компонент какого цвета преобладает в изображении: красного, зеленого или синего.  
  
 [!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_4.cpp)]  
  
 Следующая функция, `GetEncoderClsid`, получает идентификатор класса для данного типа MIME кодировщика.  Приложение использует эту функцию, чтобы получить кодировщик для растрового изображения.  
  
 [!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_5.cpp)]  
  
 \[[Наверх](#top)\]  
  
##  <a name="network"></a> Создание сети обработки изображений  
 В этом разделе описано, как создавать сеть асинхронных блоков сообщений, выполняющих обработку каждого изображения [!INCLUDE[TLA#tla_jpeg](../Token/TLA%23tla_jpeg_md.md)] \(JPG\) в данном каталоге.  Сеть выполняет следующие операции по обработке изображений.  
  
1.  Все изображения, созданные пользователем Tom, преобразуются в оттенки серого.  
  
2.  Во всех изображениях, в которых преобладает красный цвет, удаляются зеленый и синий компоненты, затем изображение затемняется.  
  
3.  Ко всем остальным изображениям применяется тонирование сепией.  
  
 Сеть применяет только первую операцию обработки изображения, соответствующую одному из перечисленных условий.  Например, если изображение создано пользователем Tom и в нем преобладает красный цвет, оно будет только преобразовано в оттенки серого.  
  
 После выполнения операции обработки изображения сеть сохраняет его на диск в виде файла растрового изображения \(BMP\).  
  
 Ниже показано, как создать функцию, реализующую сеть обработки изображений и применяющую эту сеть ко всем изображениям [!INCLUDE[TLA#tla_jpeg](../Token/TLA%23tla_jpeg_md.md)] в данном каталоге.  
  
#### Создание сети обработки изображений  
  
1.  Создайте функцию `ProcessImages`, которая принимает имя каталога на диске.  
  
     [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_6.cpp)]  
  
2.  В функции `ProcessImages` создайте переменную `countdown_event`.  Класс `countdown_event` показан далее в этом пошаговом руководстве.  
  
     [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_7.cpp)]  
  
3.  Создайте объект [std::map](../Topic/map%20Class.md), связывающий объект `Bitmap` с исходным именем файла.  
  
     [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_8.cpp)]  
  
4.  Добавьте следующий код, чтобы определить члены сети обработки изображений.  
  
     [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_9.cpp)]  
  
5.  Добавьте следующий код, чтобы соединить сеть.  
  
     [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_10.cpp)]  
  
6.  Добавьте следующий код, чтобы отправить в начало сети полный путь каждого файла [!INCLUDE[TLA#tla_jpeg](../Token/TLA%23tla_jpeg_md.md)] в каталоге.  
  
     [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_11.cpp)]  
  
7.  Подождите, пока переменная `countdown_event` не достигнет нуля.  
  
     [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_12.cpp)]  
  
 В следующей таблице описаны члены сети.  
  
|Член|Описание|  
|----------|--------------|  
|`load_bitmap`|Объект [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md), загружающий объект `Bitmap` с диска и добавляющий запись в объект `map`, связывающую изображение с исходным именем файла.|  
|`loaded_bitmaps`|Объект [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md), отправляющий загруженные изображения фильтрам обработки изображений.|  
|`grayscale`|Объект `transformer`, преобразующий в оттенки серого изображения, созданные пользователем Tom.  Он использует метаданные изображения, чтобы определить создавшего его пользователя.|  
|`colormask`|Объект `transformer`, удаляющий компоненты зеленого и синего цветов из изображений, в которых преобладает красный цвет.|  
|`darken`|Объект `transformer`, затемняющий изображения, в которых преобладает красный цвет.|  
|`sepiatone`|Объект `transformer`, применяющий тонирование сепией к изображениям, не созданным пользователем Tom и в которых не преобладает красный цвет.|  
|`save_bitmap`|Объект `transformer`, сохраняющий обработанный объект `image` на диск в качестве растрового изображения.  `save_bitmap` получает исходное имя файла из объекта `map` и изменяет расширение имени файла на BMP.|  
|`delete_bitmap`|Объект `transformer`, освобождающий память для изображений.|  
|`decrement`|Объект [concurrency::call](../../parallel/concrt/reference/call-class.md), действующий как конечный узел сети.  Он уменьшает объект `countdown_event`, чтобы сообщить главному приложению о том, что изображение обработано.|  
  
 Буфер сообщений `loaded_bitmaps` важен, так как будучи объектом `unbounded_buffer`, он предлагает объекты `Bitmap` нескольким получателям.  Когда целевой блок принимает объект `Bitmap`, объект `unbounded_buffer` не предлагает этот объект `Bitmap` другим целевым блокам.  Поэтому важен порядок связывания объектов с объектом `unbounded_buffer`.  Блоки сообщений `grayscale`, `colormask` и `sepiatone` используют фильтры, чтобы принимать только определенные объекты `Bitmap`.  Буфер сообщений `decrement` является важным целевым объектом буфера сообщений `loaded_bitmaps`, так как он принимает все объекты `Bitmap`, отклоненные другими буферами сообщений.  Объект `unbounded_buffer` необходим для распространения сообщений в определенном порядке.  Поэтому объект `unbounded_buffer` блокируется до тех пор, пока к нему не будет привязан новый целевой блок, и принимает сообщение, не принятое ни одним текущим целевым блоком.  
  
 Если в приложении необходимо, чтобы сообщение обрабатывалось несколькими блоками сообщений, а не одним блоком, первым принявшим сообщение, можно использовать другой тип блока сообщений, например `overwrite_buffer`.  Класс `overwrite_buffer` может содержать только одно сообщение, но он распространяет его всем целевым объектам.  
  
 На следующем рисунке показана сеть обработки изображений.  
  
 ![Сеть обработки изображений](../Image/ConcRT_ImageProc.png "ConcRT\_ImageProc")  
  
 Объект `countdown_event` в этом примере позволяет сети обработки изображений сообщать главному приложению о том, что все изображения обработаны.  Класс `countdown_event` использует объект [concurrency::event](../Topic/event%20Class.md), чтобы сообщить, что значение счетчика достигло нуля.  Главное приложение увеличивает счетчик при каждой отправке имени файла в сеть.  Конечный узел сети уменьшает счетчик после обработки каждого изображения.  Когда главное приложение завершает проход заданного каталога, оно ожидает, пока объект `countdown_event` не сообщит, что его счетчик достиг нуля.  
  
 В следующем примере показан класс `countdown_event`:  
  
 [!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_13.cpp)]  
  
 \[[Наверх](#top)\]  
  
##  <a name="complete"></a> Полный код примера  
 Ниже приведен полный пример кода.  Функция `wmain` управляет библиотекой [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] и вызывает функцию `ProcessImages`, чтобы обработать файлы [!INCLUDE[TLA#tla_jpeg](../Token/TLA%23tla_jpeg_md.md)] в каталоге `Sample Pictures`.  
  
 [!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-image-processing-network_14.cpp)]  
  
 На следующем рисунке показан пример результатов.  Исходные изображения расположены над соответствующими измененными изображениями.  
  
 ![Пример выходных данных для данного примера](../../parallel/concrt/media/concrt_imageout.png "ConcRT\_ImageOut")  
  
 Изображение `Lighthouse` создано пользователем Tom Alphin, поэтому оно преобразовано в оттенки серого.  В изображениях `Chrysanthemum`, `Desert`, `Koala` и `Tulips` преобладает красный цвет, поэтому из них удалены компоненты синего и зеленого цветов, а затем они затемнены.  Изображения `Hydrangeas`, `Jellyfish` и `Penguins` соответствуют критериям по умолчанию, поэтому тонированы сепией.  
  
 \[[Наверх](#top)\]  
  
### Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `image-processing-network.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/DUNICODE \/EHsc image\-processing\-network.cpp \/link gdiplus.lib**  
  
## См. также  
 [Пошаговые руководства по среде выполнения с параллелизмом](../Topic/Concurrency%20Runtime%20Walkthroughs.md)