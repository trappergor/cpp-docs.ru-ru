---
title: "__getmainargs, __wgetmainargs | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
dev_langs:
- C++
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bd386aba0f5693538d9aae61bcf7c2384b6052bd
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs, __wgetmainargs
Вызывает синтаксический анализ командной строки и снова копирует аргументы в `main()` через переданные указатели.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `_Argc`  
 Целое число, которое содержит число аргументов, передаваемых в `argv`. Параметр `argc` всегда больше или равен 1.  
  
 `_Argv`  
 Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки. По правилам `argv[0]` — это команда, с помощью которой вызывается программа, а argv[1] — это первый аргумент командной строки и так далее до аргумента argv[argc], который всегда имеет значение NULL. Первый аргумент командной строки — всегда `argv[1]`, а последний — `argv[argc - 1]`.  
  
 `_Env`  
 Массив строк, которые представляют переменные, заданные в среде пользователя. Этот массив завершается записью NULL.  
  
 `_DoWildCard`  
 Целое число, которое, если имеет значение 1, разворачивает подстановочные знаки в аргументах командной строки, а если имеет значение 0, не выполняет никаких действий.  
  
 `_StartInfo`  
 Другие сведения, передаваемые в DLL CRT.  
  
## <a name="return-value"></a>Возвращаемое значение  
 0 в случае успешного выполнения; отрицательное значение, если операция завершилась неудачей.  
  
## <a name="remarks"></a>Примечания  
 Используйте `__getmainargs` на платформах без расширенных символов и `__wgetmainargs` на платформах расширенных символов (Unicode).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|__getmainargs|internal.h|  
|__wgetmainargs|internal.h|
