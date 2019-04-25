---
title: Практическое руководство. Использование лимита подписки для задержек
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: d74a081f71f044cab90a8e6fdc64530eaaf87ed8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159942"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Практическое руководство. Использование лимита подписки для задержек

Превышение лимита подписки может повысить общую эффективность некоторых приложений, которые содержат задачи, которые имеют большой объем задержки. В этом разделе описывается использование лимита подписки для смещения задержки, вызванной чтение данных из сетевого подключения.

## <a name="example"></a>Пример

В этом примере используется [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) для загрузки файлов с HTTP-серверов. `http_reader` Класс является производным от [concurrency::agent](../../parallel/concrt/reference/agent-class.md) и использует передачу сообщений для асинхронного чтения имен URL-адрес для загрузки.

`http_reader` Класс использует [concurrency::task_group](reference/task-group-class.md) класс для параллельного чтения всех файлов. Каждая задача вызывает [Concurrency::Context:: Oversubscribe](reference/context-class.md#oversubscribe) метод с `_BeginOversubscription` параметру присвоить **true** чтобы разрешить превышение лимита подписки в текущем контексте. Каждая задача затем использует Microsoft Foundation Classes (MFC) [CInternetSession](../../mfc/reference/cinternetsession-class.md) и [CHttpFile](../../mfc/reference/chttpfile-class.md) классы для загрузки файла. Наконец, каждая задача вызывает `Context::Oversubscribe` с `_BeginOversubscription` параметру присвоить **false** отключить превышение лимита подписки.

Если превышение лимита подписки включена, среда выполнения создает один дополнительный поток, в котором будут выполняться задачи. Каждый из этих потоков можно также превышать лимит подписки текущего контекста и таким образом, создать дополнительные потоки. `http_reader` Класс использует [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объекта, чтобы ограничить количество потоков, используемых приложением. Агент инициализирует буфер с фиксированным числом значений маркера. Для каждой операции загрузки агент считывает значение токена из буфера до начала операции, затем записывает это значение обратно в буфер после завершения операции. Если буфер пуст, агент ожидает в течение одной из операций загрузки будет записано значение в буфер.

Следующий пример ограничивает количество одновременно выполняемых задач в два раза число доступных аппаратных потоков. Это значение является хорошей отправной точкой для использования при экспериментах с превышением лимита подписки. Можно использовать значение, соответствующее конкретной вычислительной среде, или динамически изменять это значение, чтобы реагировать на них фактических рабочих нагрузок.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

В этом примере получается следующий результат на четырехпроцессорном компьютере:

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

Данный пример может выполняться быстрее при включении превышение лимита подписки, так как выполнение дополнительных задач, пока другие задачи ожидают долго выполняющихся операций до конца.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `download-oversubscription.cpp` и затем выполняется один из следующих команд в **Командная строка Visual Studio** окна.

**/ MD /D «_AFXDLL» CL.exe/EHsc download-oversubscription.cpp**

**/ EHsc/MT CL.exe download-oversubscription.cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Следует всегда отключите превышение лимита подписки после ее больше не требуется. Рассмотрим функцию, которая не обрабатывает исключение, вызванное другую функцию. Если вы не отключили превышение лимита подписки до выполнения возврата функцией, любая дополнительная параллельная работа также будет превышать лимит подписки текущего контекста.

Можно использовать *Получение ресурса есть инициализация* шаблон (RAII) для ограничения превышение лимита подписки для заданной области. В разделе шаблон RAII структуру данных выделена в стеке. Что инициализирует структуры данных, или получает ресурса при его создании и уничтожает или освобождает ресурс, при уничтожении структуре данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Таким образом, ресурс надлежащее управление при возникновении исключения или если функция содержит несколько `return` инструкций.

В следующем примере определяется структура, которая называется `scoped_blocking_signal`. Конструктор `scoped_blocking_signal` структура позволяет превышение лимита подписки, а деструктор отключает превышение лимита подписки.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

В следующем примере изменяется текст `download` метод использовать RAII для обеспечения превышения лимита подписки запрещено раньше, функция возвращает. Этот метод гарантирует, что `download` метод исключений.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>См. также

[Контексты](../../parallel/concrt/contexts.md)<br/>
[Метод Context::Oversubscribe](reference/context-class.md#oversubscribe)
