---
title: "Обработчик конкретного языка | Microsoft Docs"
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
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Обработчик конкретного языка
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Относительный адрес обработчика языка присутствует в UNWIND\_INFO, когда бы ни были установлены флаги UNW\_FLAG\_EHANDLER или UNW\_FLAG\_UHANDLER.  Как описано в предыдущем разделе, обработчик языка вызывается как часть поиска обработчика исключения или часть раскрутки.  Он имеет следующий прототип:  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** предоставляет указатель на запись исключения, имеющий стандартное определение Win64.  
  
 **EstablisherFrame** представляет собой адрес базы фиксированного расположения стека для данной функции.  
  
 **ContextRecord** указывает на контекст исключения во время его возникновения \(в случае если задействован обработчик событий\) или текущий контекст "раскрутки" \(в случае если задействован обработчик завершения\).  
  
 **DispatcherContext** указывает на контекст диспетчера для данной функции.  Он имеет следующее определение:  
  
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
  
 **ControlPc** представляет собой значение RIP в рамках данной функции.  Это может быть адрес исключения или адрес, на котором элемент прекратил функцию установления.  Этот RIP будет использоваться для определения, находится ли элемент управления в рамках защищенной конструкции в данной функции \(например, блок \_\_try для \_\_try\/\_\_except или \_\_try\/\_\_finally\).  
  
 **ImageBase** представляет собой основу образа \(адрес загрузки\) модуля, содержащего данную функцию, которую необходимо добавить в 32\-битные смещения, используемые в записи функции, а также в информации раскрутки для записи относительных адресов.  
  
 **FunctionEntry** предоставляет указатель записи функции RUNTIME\_FUNCTION, содержащей саму функцию и относительные адреса информации раскрутки основного образа для данной функции.  
  
 **EstablisherFrame** представляет собой адрес базы фиксированного расположения стека для данной функции.  
  
 **TargetIp** предоставляет адреса выборочных инструкций, указывающие дополнительные адреса раскрутки.  Этот адрес пропускается, если не было указано **EstablisherFrame**.  
  
 **ContextRecord** указывает на контекст исключения, используемый кодом диспетчеризации или раскрутки системного исключения.  
  
 **LanguageHandler** указывает на подпрограмму вызванного языкового обработчика.  
  
 **HandlerData** указывает на данные языкового обработчика для данной функции.  
  
## См. также  
 [Обработка исключений \(x64\)](../build/exception-handling-x64.md)