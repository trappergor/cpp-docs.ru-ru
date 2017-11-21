---
title: "Предупреждение средств компоновщика LNK4098 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4098
dev_langs: C++
helpviewer_keywords: LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0acc9ba4a43e37712e3643b49975fc15a4cce280
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4098"></a>Предупреждение средств компоновщика LNK4098
DEFAULTLIB «библиотека» противоречит использованию других библиотек; использовать /NODEFAULTLIB:library  
  
 Вы пытаетесь связи с несовместимыми библиотеками.  
  
> [!NOTE]
>  Библиотеки времени выполнения теперь содержат директивы для предотвращения смешивания различных типов. Вы получите это предупреждение при попытке использовать разные типы или отладки и неотладочные версии библиотеки времени выполнения в одной программе. Например если один файл для использования одной библиотеки типа времени выполнения, а другой файл для использования другого типа (например, однопоточной и многопоточной) и попытке связать эти скомпилирован, получите это предупреждение. Следует компилировать все исходные файлы для использования одной и той же библиотеки времени выполнения. В разделе [использование библиотеки времени выполнения](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **/MT**, **/LD**) параметров компилятора для получения дополнительной информации.  
  
 Можно использовать компоновщика [/verbose: LIB](../../build/reference/verbose-print-progress-messages.md) коммутатора, чтобы определить, какие библиотеки ищет компоновщик. Если появляется ошибка LNK4098 и необходимо создать исполняемый файл, который использует, к примеру, однопоточные, библиотеки времени выполнения, используйте **/verbose: LIB** параметр, чтобы определить, какие библиотеки ищет компоновщик. Компоновщик следует печатать LIBC.lib и не LIBCMT.lib, MSVCRT.lib, LIBCD.lib, LIBCMTD.lib или библиотеки MSVCRTD.lib как искомых библиотек. Можно указать компоновщику игнорировать некорректные библиотеки времени выполнения с помощью [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) для каждой библиотеки, которую следует игнорировать.  
  
 В следующей таблице показано, какие библиотеки следует игнорировать в зависимости от того, библиотеку времени выполнения, в которой вы хотите использовать.  
  
|Чтобы использовать эту библиотеку времени выполнения|Игнорировать эти библиотеки|  
|-----------------------------------|----------------------------|  
|Одним потоком (libc.lib)|LIBCMT.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Многопоточный (libcmt.lib)|Libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Многопоточные с использованием библиотеки DLL (msvcrt.lib)|Libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Отладка одним потоком (libcd.lib)|Libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|Отладка многопоточного (libcmtd.lib)|Libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|Отладочные многопоточные с использованием библиотеки DLL (msvcrtd.lib)|Libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 Например если получено это предупреждение, и вы хотите создать исполняемый файл, который использует неотладочных, однопоточную версию библиотеки времени выполнения, можно использовать следующие параметры при этом Компоновщик:  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```