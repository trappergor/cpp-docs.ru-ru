---
title: "Как: использование лимита подписки для устранения задержек | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7159d5489459bd32566c8665a5bbf42337fd8837
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Практическое руководство. Использование лимита подписки для устранения задержек
Превышение лимита подписки может повысить общую эффективность некоторых приложений, которые содержат задачи, которые имеют большое количество задержки. В этом разделе описывается использование лимита подписки для смещения задержки, вызванные чтение данных из сетевого подключения.  
  
## <a name="example"></a>Пример  
 В этом примере используется [библиотеки асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md) для загрузки файлов с HTTP-серверами. `http_reader` Класс является производным от [concurrency::agent](../../parallel/concrt/reference/agent-class.md) и использует передачу сообщений для асинхронного чтения URL-имен для загрузки.  
  
 `http_reader` Класс использует [concurrency::task_group](reference/task-group-class.md) класса для параллельного чтения всех файлов. Каждая задача вызывает [Concurrency::Context:: Oversubscribe](reference/context-class.md#oversubscribe) метод с `_BeginOversubscription` равным `true` чтобы разрешить превышение лимита подписки в текущем контексте. Каждая задача затем использует Microsoft Foundation Classes (MFC) [CInternetSession](../../mfc/reference/cinternetsession-class.md) и [CHttpFile](../../mfc/reference/chttpfile-class.md) классы для загрузки файла. Наконец, каждая задача вызывает `Context::Oversubscribe` с `_BeginOversubscription` равным `false` отключить превышение лимита подписки.  
  
 Если включено превышение лимита подписки, среда выполнения создает один дополнительный поток, в котором будут выполняться задачи. Каждый из этих потоков может также превышать лимит подписки текущего контекста и таким образом, создать дополнительные потоки. `http_reader` Класс использует [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объекта ограничивает число потоков, которые используются приложением. Агент инициализирует буфер с фиксированным числом значений маркера. Для каждой операции загрузки агент считывает значение токена из буфера до начала операции, затем записывает это значение обратно в буфер после завершения операции. Если буфер пуст, агент ожидает один из операций загрузки, чтобы записать значение в буфер.  
  
 В следующем примере ограничиваются количество одновременно выполняемых задач в два раза количество доступных аппаратных потоков. Это значение является хорошей отправной точкой для использования при экспериментах с превышение лимита подписки. Можно использовать значение, подходящее конкретной вычислительной среде, или динамически изменять это значение в соответствии с фактической рабочей нагрузкой.  
  
 [!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]  
  
 В этом примере выводятся следующие данные на четырехпроцессорном компьютере:  
  
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
  
 Данный пример может выполняться быстрее при включении превышение лимита подписки, так как выполнение дополнительных задач, пока другие задачи ожидать завершения выполняющихся операций.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `download-oversubscription.cpp` и затем выполните одну из следующих команд в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc/MD /D «_AFXDLL» download-oversubscription.cpp**  
  
 **/ EHsc/MT CL.exe download-oversubscription.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Всегда отключите превышение лимита подписки после больше не требуется. Рассмотрим функцию, которая не обрабатывает исключение, вызванное другой функции. Если не отключить превышение лимита подписки до выполнения возврата функцией, любая дополнительная параллельная работа также будет превышать лимит подписки текущего контекста.  
  
 Можно использовать *Получение ресурса есть инициализация* шаблон (RAII) для ограничения превышения лимита подписки для данной области. При использовании шаблона RAII структура данных выделяется в стеке. Что структуры данных инициализирует или приобретает ресурс, когда он создается и уничтожает или освобождает ресурс, при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Таким образом, ресурс эффективно управляется при возникновении исключения или если функция содержит несколько `return` инструкции.  
  
 В следующем примере определяется структура, которая называется `scoped_blocking_signal`. Конструктор `scoped_blocking_signal` структуры включает превышение лимита подписки, а деструктор отключает превышение лимита подписки.  
  
 [!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]  
  
 В следующем примере изменяется текст `download` метод, используемый для обеспечения превышения лимита подписки RAII отключена до выполнения возврата функцией. Этот метод гарантирует, что `download` метод исключений.  
  
 [!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Контексты](../../parallel/concrt/contexts.md)   
 [Метод Context::Oversubscribe](reference/context-class.md#oversubscribe)


