---
title: "Обработчик конкретного языка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc15e730666a643dfaa028fe7bc6166144897308
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="language-specific-handler"></a>Обработчик конкретного языка
Относительный адрес обработчик конкретного языка в UNWIND_INFO отсутствует, каждый раз, когда установлены флаги UNW_FLAG_EHANDLER или UNW_FLAG_UHANDLER. Как описано в предыдущем разделе, обработчик языка вызывается как часть поиска для обработчика исключений или в процессе очистки. Он имеет следующий прототип:  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** предоставляет указатель на запись исключения, имеющий стандартное определение Win64.  
  
 **EstablisherFrame** адрес базового выделения основных стека для этой функции.  
  
 **ContextRecord** указывает на контекст исключения во время возникновения исключения (в случае обработчик исключений), либо текущий контекст «раскрутки» (в случае обработчик завершения).  
  
 **DispatcherContext** указывает диспетчер контекст для этой функции. Он имеет следующее определение:  
  
```  
typedef struct _DISPATCHER_CONTEXT {  
    ULONG64 ControlPc;  
    ULONG64 ImageBase;  
    PRUNTIME_FUNCTION FunctionEntry;  
    ULONG64 EstablisherFrame;  
    ULONG64 TargetIp;  
    PCONTEXT ContextRecord;  
    PEXCEPTION_ROUTINE LanguageHandler;  
    PVOID HandlerData;  
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;  
```  
  
 **ControlPc** значение RIP в рамках данной функции. Это адрес исключения или адрес, на котором элемент прекратил функцию установления. Это RIP, который будет использоваться для определения, если элемент управления находится внутри защищенной конструкции в данной функции (например, блок __try для \__try /\__except или \__try /\__finally).  
  
 **ImageBase** представляет собой основу образа (адрес загрузки) модуля, содержащего данную функцию, которую добавлен 32-разрядные смещения, используемые в записи функции и раскрутки для записи относительных адресов.  
  
 **FunctionEntry** питания указателем RUNTIME_FUNCTION функцию записи, содержащий функцию и очистки относительные адреса база образа сведения для этой функции.  
  
 **EstablisherFrame** адрес базового выделения основных стека для этой функции.  
  
 **TargetIp** предоставляющий необязательное инструкция адрес, указывающий адрес продолжения очистка. Этот адрес учитывается, если **EstablisherFrame** не указан.  
  
 **ContextRecord** указывает на контекст исключения для использования кодом диспетчеризации или раскрутки системы исключения.  
  
 **LanguageHandler** указывает языкового подпрограмму обработчика вызывается.  
  
 **HandlerData** указывает на данные языкового обработчика для этой функции.  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений (x64)](../build/exception-handling-x64.md)