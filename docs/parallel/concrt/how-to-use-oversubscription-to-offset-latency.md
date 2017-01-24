---
title: "Практическое руководство. Использование лимита подписки для устранения задержек | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "превышение лимита подписки, использование [среда выполнения с параллелизмом]"
  - "использование превышения лимита подписки [среда выполнения с параллелизмом]"
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование лимита подписки для устранения задержек
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Превышение лимита подписки может повысить общую эффективность некоторых приложений, содержащих задачи с большими задержками.  В этом разделе показано, как использовать превышение лимита подписки для компенсации задержки, вызванной чтением данных из сетевого подключения.  
  
## Пример  
 В этом примере для загрузки файлов с HTTP\-серверов используется библиотека [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md).  Класс `http_reader` наследуется от класса [Concurrency::agent](../../parallel/concrt/reference/agent-class.md) и использует передачу сообщений для асинхронного чтения URL\-имен, которые требуется загрузить.  
  
 Класс `http_reader` использует класс [Concurrency::task\_group](../Topic/task_group%20Class.md) для параллельного чтения всех файлов.  Каждая задача вызывает метод [Concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md), в котором для параметра `_BeginOversubscription` задано значение `true`, чтобы разрешить превышение лимита подписки в текущем контексте.  Затем каждая задача использует классы библиотеки Microsoft Foundation Classes \(MFC\) [CInternetSession](../Topic/CInternetSession%20Class.md) и [CHttpFile](../Topic/CHttpFile%20Class.md) для загрузки файла.  Наконец, каждая задача вызывает метод `Context::Oversubscribe`, в котором для параметра `_BeginOversubscription` задано значение `false`, чтобы отключить превышение лимита подписки.  
  
 Если включено превышение лимита подписки, среда выполнения создает по одному дополнительному потоку, в котором будут выполняться задачи.  Каждый из этих потоков также может использовать превышение лимита подписки в текущем контексте и, таким образом, создать дополнительные потоки.  Класс `http_reader` использует объект [Concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) для ограничения количества потоков, используемых приложением.  Агент инициализирует буфер с использованием фиксированного числа значений токенов.  Для каждой операции загрузки агент считывает значение токена из буфера до начала операции, затем записывает это значение обратно в буфер после завершения операции.  Если буфер пуст, агент ожидает, пока одна из операций загрузки запишет значение обратно в буфер.  
  
 В приведенном ниже примере количество одновременно выполняемых задач ограничено числом доступных аппаратных потоков, умноженным на два.  Это значение является хорошей отправной точкой при экспериментах с превышением лимита подписки.  Можно использовать значение, подходящее конкретной вычислительной среде, или динамически изменять это значение в соответствии с фактической рабочей нагрузкой.  
  
 [!CODE [concrt-download-oversubscription#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#1)]  
  
 На четырехпроцессорном компьютере этот пример создает следующие выходные данные.  
  
  **Downloading http:\/\/www.adatum.com\/...**  
**Downloading http:\/\/www.adventure\-works.com\/...**  
**Downloading http:\/\/www.alpineskihouse.com\/...**  
**Downloading http:\/\/www.cpandl.com\/...**  
**Downloading http:\/\/www.cohovineyard.com\/...**  
**Downloading http:\/\/www.cohowinery.com\/...**  
**Downloading http:\/\/www.cohovineyardandwinery.com\/...**  
**Downloading http:\/\/www.contoso.com\/...**  
**Downloading http:\/\/www.consolidatedmessenger.com\/...**  
**Downloading http:\/\/www.fabrikam.com\/...**  
**Downloading http:\/\/www.fourthcoffee.com\/...**  
**Downloading http:\/\/www.graphicdesigninstitute.com\/...**  
**Downloading http:\/\/www.humongousinsurance.com\/...**  
**Downloading http:\/\/www.litwareinc.com\/...**  
**Downloading http:\/\/www.lucernepublishing.com\/...**  
**Downloading http:\/\/www.margiestravel.com\/...**  
**Downloading http:\/\/www.northwindtraders.com\/...**  
**Downloading http:\/\/www.proseware.com\/...**  
**Downloading http:\/\/www.fineartschool.net...**  
**Downloading http:\/\/www.tailspintoys.com\/...**  
**Downloaded 1801040 bytes in 3276 ms.** Данный пример может выполняться быстрее при включенном превышении лимита подписки, потому что возможно выполнение дополнительных задач, пока другие задачи ожидают завершения долго выполняющихся операций.  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `download-oversubscription.cpp`, затем выполните в окне командной строки одну из следующих команд.  
  
 **cl.exe \/EHsc \/MD \/D "\_AFXDLL" download\-oversubscription.cpp**  
  
 **cl.exe \/EHsc \/MT download\-oversubscription.cpp**  
  
## Отказоустойчивость  
 Обязательно выключайте превышение лимита подписки, если оно больше не требуется.  Рассмотрим функцию, которая не обрабатывает исключение, созданное другой функцией.  Если перед возвратом функции не отключить превышение лимита подписки, любая дополнительная параллельная работа будет также использовать превышение лимита подписки текущего контекста.  
  
 Для ограничения превышения лимита подписки до заданного масштаба можно воспользоваться шаблоном *Получение ресурса есть инициализация* \(RAII\).  При использовании шаблона RAII структура данных располагается в стеке.  Эта структура данных инициализирует или приобретает ресурс во время создания структуры и уничтожает или освобождает ресурс во время уничтожения структуры данных.  Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости.  Следовательно, ресурс эффективно управляется при создании исключения или если функция содержит несколько операторов `return`.  
  
 В следующем примере определяется структура с именем `scoped_blocking_signal`.  Конструктор структуры `scoped_blocking_signal` включает превышение лимита подписки, а деструктор отключает превышение лимита подписки.  
  
 [!CODE [concrt-download-oversubscription#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#2)]  
  
 В следующем примере тело метода `download` изменяется таким образом, чтобы он использовал шаблон RAII для обеспечения отключения превышения лимита подписки перед возвратом функции.  Эта техника обеспечивает безопасность метода `download` в случае возникновения исключений.  
  
 [!CODE [concrt-download-oversubscription#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-download-oversubscription#3)]  
  
## См. также  
 [Контексты](../../parallel/concrt/contexts.md)   
 [Метод Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md)