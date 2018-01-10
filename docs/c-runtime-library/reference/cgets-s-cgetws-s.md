---
title: "_cgets_s _cgetws_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
dev_langs: C++
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28e35d5f2eb2f07cd1b02fa8b1edc3f41b2c2174
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cgetss-cgetwss"></a>_cgets_s, _cgetws_s
Возвращает строку символов из консоли. Это версии функций [_cgets и _cgetws](../../c-runtime-library/cgets-cgetws.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _cgets_s(   
   char *buffer,  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
errno_t _cgetws_s(  
   wchar_t *buffer  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
template <size_t size>  
errno_t _cgets_s(   
   char (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
template <size_t size>  
errno_t _cgetws_s(  
   wchar_t (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `buffer`  
 Место хранения данных.  
  
 [in] `numberOfElements`  
 Размер буфера в однобайтовых или расширенных символах, который также представляет максимальное число символов для чтения.  
  
 [in] `pSizeRead`  
 Число фактически прочитанных символов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении возвращается ноль, в противном случае возвращается код ошибки.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`buffer`|`numberOfElements`|`pSizeRead`|Назад|Содержимое `buffer`|  
|--------------|------------------------|-----------------|------------|--------------------------|  
|`NULL`|any|any|`EINVAL`|Н/Д|  
|не `NULL`|нуль|any|`EINVAL`|не изменено|  
|не `NULL`|any|`NULL`|`EINVAL`|строка нулевой длины|  
  
## <a name="remarks"></a>Примечания  
 `_cgets_s` и `_cgetws_s` читают строки из консоли и копируют ее (с нулевым признаком конца) в `buffer`. `_cgetws_s` — версия функции для расширенных символов. За исключением размера символа, поведение этих двух функций идентично. Максимальный размер строки для чтения передается в качестве параметра `numberOfElements`. Размер должен учитывать дополнительный символ для конечного нуля. Число фактически считанных символов помещается в `pSizeRead`.  
  
 Если во время операции или при проверке параметров возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, для `errno` задается значение `EINVAL` и возвращается значение `EINVAL`.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные функции могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts_s`|`_cgets_s`|`_cgets_s`|`_cgetws_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_cgets_s`|\<conio.h>|  
|`_cgetws_s`|\<conio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)