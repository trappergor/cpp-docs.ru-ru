---
title: "Управление потоками | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Controlling Streams
dev_langs:
- C++
helpviewer_keywords:
- streams, controlling
- controlling streams
- streams
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 4551a4a47e2fbfbb3fdc687103fbd3e4e6a47046
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="controlling-streams"></a>Управление потоками
Функция [fopen](../c-runtime-library/reference/fopen-wfopen.md) возвращает адрес объекта с типом `FILE`. Этот адрес используется в качестве аргумента `stream` в нескольких библиотечных функциях для выполнения различных операций с открытым файлом. Для байтового потока ввод выполняется так, как если бы каждый символ считывался с помощью функции [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), а вывод — как если бы каждый символ записывался с помощью функции [fputc](../c-runtime-library/reference/fputc-fputwc.md). Для потока расширенных символов ввод выполняется так, как если бы каждый символ считывался с помощью функции [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), а вывод — как если бы каждый символ записывался с помощью функции [fputwc](../c-runtime-library/reference/fputc-fputwc.md).  
  
 Можно закрыть файл, вызвав функцию [fclose](../c-runtime-library/reference/fclose-fcloseall.md), после чего адрес объекта `FILE` становится недействительным.  
  
 Объект `FILE` сохраняет состояние потока, в том числе:  
  
-   Индикатор ошибки, установленный в ненулевое значение функцией, обнаружившей ошибку чтения или записи.  
  
-   Индикатор конца файла, установленный в ненулевое значение функцией, встретившей конец файла при чтении.  
  
-   Индикатор позиции файла определяет следующий байт в потоке для чтения или записи, если файл поддерживает запросы размещения.  
  
-   [Состояние потока](../c-runtime-library/stream-states.md) сообщает, доступен ли поток для чтения и (или) записи, а также является ли поток непривязанным, байтовым или расширенным символьным.  
  
-   Состояние преобразования запоминает состояние любого частично собранного или созданного обобщенного многобайтового символа, а также все состояния сдвига для последовательности байтов в файле.  
  
-   Файловый буфер указывает адрес и размер объекта массива, который может использоваться библиотечными функциями для повышения производительности операций чтения и записи потока.  
  
 Не изменяйте никакие значения, хранящиеся в объекте `FILE` или файловом буфере, указанном для использования с этим объектом. Невозможно скопировать объект `FILE` и переносимо использовать адрес копии в качестве аргумента `stream` библиотечной функции.  
  
## <a name="see-also"></a>См. также  
 [Файлы и потоки](../c-runtime-library/files-and-streams.md)
