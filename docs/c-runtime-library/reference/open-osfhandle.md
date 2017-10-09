---
title: "_open_osfhandle | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open_osfhandle
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8d214df5d1e1cd3a48336723cecbf530402eafe3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="openosfhandle"></a>_open_osfhandle
Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `osfhandle`  
 Дескриптор файла операционной системы.  
  
 `flags`  
 Разрешенные типы операций.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения функция `_open_osfhandle` возвращает дескриптор файла времени выполнения C. В противном случае возвращается значение -1.  
  
## <a name="remarks"></a>Примечания  
 Функция `_open_osfhandle` выделяет дескриптор файла времени выполнения C и связывает его с дескриптором файла операционной системы, указанным функцией `osfhandle`. Аргумент `flags` представляет собой целочисленное выражение, сформированное на базе одной или нескольких констант манифеста, которые определяются в файле Fcntl.h. Если несколько констант манифеста используются для формирования аргумента `flags`, константы объединяются с помощью битового оператора ИЛИ ( **&#124;** ).  
  
 Файл Fcntl.h определяет следующие константы манифеста.  
  
 **_O_APPEND**  
 Помещает указатель файла в конец файла перед каждой операцией записи.  
  
 **_O_RDONLY**  
 Открывает файл только для чтения.  
  
 **_O_TEXT**  
 Открывает файл в текстовом режиме (с преобразованием).  
  
 **_O_WTEXT**  
 Открывает файл в режиме Юникода (с преобразованием UTF-16).  
  
 Чтобы закрыть файл, открытый с помощью функции `_open_osfhandle`, вызовите функцию `_close`. При вызове функции `_close` базовый дескриптор также закрывается, поэтому не нужно вызывать функцию `CloseHandle` Win32 для исходного дескриптора.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)
