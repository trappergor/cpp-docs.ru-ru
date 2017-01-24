---
title: "Параметры EDITBIN | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Программа EDITBIN, параметры"
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметры EDITBIN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Можно использовать EDITBIN изменение объектных файлов, исполняемых файлов, библиотек динамической компоновки \(DLLs\).  Эти параметры определяют изменения, EDITBIN действий.  
  
 Имени параметра предшествует спецификатор, которым является либо знак дефиса \( – \), либо косая черта \( \/ \).  Нельзя сокращать имена параметров.  Некоторые параметры принимают аргументы, определенные после двоеточия \(: \).  Не допускается использование пробелов и символов табуляции внутри параметра.  Параметры в командной строке следует разделять одним или несколькими пробелами и символами табуляции.  Имена параметров и их аргументы ключевые слова или аргументы имени файла не учитывается регистр.  Например, привязка — и \/BIND означающие одно и то же действие.  
  
 Программа EDITBIN имеет следующие параметры:  
  
|Команда|Назначение|  
|-------------|----------------|  
|[\/ALLOWBIND](../../build/reference/allowbind.md)|Определяет, является ли библиотеки DLL можно выполнить привязку.|  
|[\/ALLOWISOLATION](../Topic/-ALLOWISOLATION.md)|Определяет расширение функциональности поиска DLL или исполняемого файла очевидным.|  
|[\/APPCONTAINER](../../build/reference/appcontainer.md)|Определяет, является ли приложение выполняется в рамках AppContainer\- для примера, приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].|  
|[\/BIND](../../build/reference/bind.md)|Задает адреса для точек входа в указанных объектов ко времени загрузки скорости.|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase.md)|Определяет, является ли DLL или исполняемый образ могут быть случайно rebased на шаге при загрузке с помощью randomization \(ASLR\) макета адресного пространства.|  
|[\/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Внутренние ошибки отчетов в Майкрософт.|  
|[\/HEAP](../../build/reference/heap.md)|Задает размер кучи\) в байтах образа.|  
|[\/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Определяет, поддерживает ли библиотека DLL или исполняемый образ высокий randomization \(ASLR\) макета адресного пространства энтропии \(64 бита\).|  
|[\/INTEGRITYCHECK](../Topic/-INTEGRITYCHECK.md)|Определяет, следует ли проверять цифровые подписи во время загрузки.|  
|[\/LARGEADDRESSAWARE](../Topic/-LARGEADDRESSAWARE.md)|Определяет, поддерживает ли объект адреса, размер которых превышает 2 гигабайта.|  
|[\/NOLOGO](../../build/reference/nologo-editbin.md)|Отключает баннер запуска EDITBIN.|  
|[\/NXCOMPAT](../Topic/-NXCOMPAT.md)|Определяет, является ли исполняемый образ совместим с предотвращением выполнения данных Windows.|  
|[\/REBASE](../Topic/-REBASE.md)|Задает базовые адреса для указанных объектов.|  
|[\/RELEASE](../../build/reference/release.md)|Задает контрольной суммы в заголовке.|  
|[\/SECTION](../Topic/-SECTION%20\(EDITBIN\).md)|Переопределяет атрибуты секции.|  
|[\/STACK](../../build/reference/stack.md)|Задает размер стека\) в байтах образа.|  
|[\/SUBSYSTEM](../../build/reference/subsystem.md)|Определяет среду выполнения.|  
|[\/SWAPRUN](../../build/reference/swaprun.md)|Указывает, что изображение исполняемого файла, из которого должны быть скопированы на файл подкачки, а затем запускается оттуда.|  
|[\/TSAWARE](../../build/reference/tsaware.md)|Указывает, что приложение предназначено для выполнения на основе нескольких пользователей.|  
|[\/VERSION](../../build/reference/version.md)|Задает номер версии в заголовке.|  
  
## См. также  
 [Средства построения С\/C\+\+](../Topic/C-C++%20Build%20Tools.md)   
 [Справочник ЕDITBIN](../Topic/EDITBIN%20Reference.md)