---
title: Обработчик конкретного языка
ms.date: 11/04/2016
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
ms.openlocfilehash: f355c0578cdf898dbe8880b2c839cac5634dcbf4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596336"
---
# <a name="language-specific-handler"></a>Обработчик конкретного языка

Относительный адрес обработчик конкретного языка присутствует в UNWIND_INFO всякий раз, когда флаги UNW_FLAG_EHANDLER или UNW_FLAG_UHANDLER установлены. Как описано в предыдущем разделе, вызывается обработчик конкретного языка, как часть поиска обработчика исключений или как часть очистка. Он имеет следующий прототип:

```
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** предоставляет указатель на запись исключения, имеющий стандартное определение Win64.

**EstablisherFrame** — это адрес базового выделения основных стека для этой функции.

**ContextRecord** указывает на контекст исключения во время (в случае обработчик исключений) было создано исключение или текущего «очистить» контекста (в случае обработчик завершения).

**DispatcherContext** указывает на контекст dispatcher для этой функции. Он имеет следующее определение:

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

**ControlPc** является значением зарезервированного IP-адреса в пределах этой функции. Это адрес исключения или адрес, по которому элемент управления влево функцию установления. Это RIP, который будет использоваться для определения, является ли элемент управления в рамках защищенной конструкции в этой функции (например, блок __try для \__try /\__except или \__try /\__finally).

**"Imagebase"** представляет собой основу образа (адрес загрузки) модуля, содержащего данную функцию, добавляемым к 32-разрядные смещения, используемые в функции записи и раскрутки для записи относительных адресов.

**FunctionEntry** указателем на RUNTIME_FUNCTION функцию записи, содержащий функцию и очистки относительные адреса основного образа сведения для этой функции.

**EstablisherFrame** — это адрес базового выделения основных стека для этой функции.

**TargetIp** предоставляет необязательный инструкции адрес, который указывает адрес продолжения очистку. Этот адрес учитывается, если **EstablisherFrame** не указан.

**ContextRecord** указывает на контекст исключения для использования в коде системы диспетчеризации или раскрутки исключение.

**LanguageHandler** указывает языкового подпрограмму обработчика вызова.

**HandlerData** указывает на данные языкового обработчика для этой функции.

## <a name="see-also"></a>См. также

[Обработка исключений (x64)](../build/exception-handling-x64.md)