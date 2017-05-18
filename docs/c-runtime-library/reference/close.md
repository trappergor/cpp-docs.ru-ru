---
title: "_close | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _close
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
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9dab323afc6c70e81592119e0cec2775c239d87f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="close"></a>_close
Закрывает файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _close(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fd`  
 Дескриптор файла, ссылающийся на открытый файл.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_close` возвращает 0, если файл был успешно закрыт. Возвращаемое значение-1 указывает на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Функция `_close` закрывает файл, связанный с `fd`.  
  
 Дескриптор файла и соответствующий обработчик файлов операционной системы закрываются. Таким образом, вызывать `CloseHandle` не требуется, если файл был открыт с помощью функции Win32 `CreateFile` и преобразован в дескриптор файлов с помощью `_open_osfhandle`.  
  
 Эта функция проверяет свои параметры. Если параметр `fd` является недопустимым дескриптором, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции возвращают значение −1 и задают для `errno` значение `EBADF`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_close`|\<io.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [_open](../../c-runtime-library/reference/open-wopen.md).  
  
## <a name="see-also"></a>См. также  
 [Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_unlink, _wunlink](../../c-runtime-library/reference/unlink-wunlink.md)
