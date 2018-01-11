---
title: "Универсальные текстовые сопоставления в файле Tchar.h | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tchar.h
dev_langs: C++
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 405e95e9eb8fb760e2688e164178cf9270f31877
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="generic-text-mappings-in-tcharh"></a>Универсальные текстовые сопоставления в файле Tchar.h
Чтобы упростить преобразование кода для международного использования [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] библиотека времени выполнения предоставляет [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-конкретных универсальные текстовые сопоставления для многих типов данных, подпрограмм и других объектов. Можно использовать эти сопоставления, которые определены в файле Tchar.h для написания универсального кода, который можно скомпилировать в однобайтовой, многобайтовой кодировке или [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] наборов, в зависимости от константы манифеста, определяется с помощью символов `#define` инструкции. Универсальные текстовые сопоставления представляют собой [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] расширения, которые не являются [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] совместимы.  
  
 С помощью Tchar.h, можно построить однобайтовые, многобайтовых символов значение (MBCS), и [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] приложения тот же источник. В файле Tchar.h определяются макросы (с префиксом `_tcs`), с помощью правильных определений препроцессора, сопоставляемые `str`, `_mbs`, или `wcs` соответствующие функции. Для использования mbsc определите символ `_MBCS`. Для построения [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], определите символ `_UNICODE`. Чтобы построить приложение и однобайтовых, определите ни (по умолчанию). По умолчанию `_MBCS` определяется для приложений MFC.  
  
 `_TCHAR` Тип данных определяется в файле Tchar.h условно. Если символ `_UNICODE` определен для построения, `_TCHAR` определяется как `wchar_t`; в противном случае в однобайтовой и многобайтовой Кодировки построений, они определены как `char`. (`wchar_t`, базовый тип данных расширенных символов Юникода, является аналогом 16-разрядное для 8-разрядное подписан `char`.) Приложения на разных языках, используйте `_tcs` семейство функций, в которых используются `_TCHAR` единицы, не в байтах. Например `_tcsncpy` копии `n` `_TCHARs`, а не `n` байт.  
  
 Так как некоторые один байт символа набор (SBCS) функции обработки строк (со знаком) `char*` параметров, приведет к Предупреждение компилятора Несоответствие типа при `_MBCS` определен. Чтобы избежать этого предупреждения тремя способами:  
  
1.  Использование преобразователей встроенных типобезопасных функций, содержащихся в файле Tchar.h. Это поведение установлено по умолчанию.  
  
2.  Использование макроса в файле Tchar.h, определив `_MB_MAP_DIRECT` в командной строке. После этого необходимо сопоставить типы вручную. Это наиболее быстрый способ, но не является строго типизированным.  
  
3.  Использование преобразователей типобезопасный статически скомпонованной библиотекой функций, содержащихся в файле Tchar.h. Для этого необходимо определить константу `_NO_INLINING` в командной строке. Это самый медленный и в то же время самый типобезопасный способ.  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>Директивы препроцессора для универсальных текстовых сопоставлений  
  
|Определение #|Скомпилированная версия|Пример|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)](расширенные символы)|`_tcsrev` сопоставляется с `_wcsrev`|  
|`_MBCS`|Многобайтовые символы|`_tcsrev` сопоставляется с `_mbsrev`|  
|Нет (по умолчанию не имеет ни `_UNICODE` ни `_MBCS` определен)|SBCS ([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)])|`_tcsrev` сопоставляется с `strrev`|  
  
 Например, универсальная текстовая функция `_tcsrev`, определяется в файле Tchar.h, сопоставляется `_mbsrev` Если вы определили `_MBCS` в программе или `_wcsrev` Если вы определили `_UNICODE`. В противном случае `_tcsrev` сопоставляется с `strrev`. Для удобства программирования в файле Tchar.h также предусмотрены другие сопоставления типа данных, но `_TCHAR` является наиболее полезным.  
  
### <a name="generic-text-data-type-mappings"></a>Сопоставления типов данных универсального текста  
  
|Универсальные текстовые<br /><br /> Имя типа данных|_UNICODE &<br /><br /> _MBCS не определены|_MBCS<br /><br /> Определено|_UNICODE<br /><br /> Определено|  
|--------------------------------------|----------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` или `_TEXT`|Не действует (удаляется препроцессором)|Не действует (удаляется препроцессором)|`L`(преобразует следующий символ или строку в ее [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] аналог)|  
  
 Список универсальных текстовых сопоставлений подпрограмм, переменных и других объектов см. в разделе [универсальные текстовые сопоставления](../c-runtime-library/generic-text-mappings.md) в справочнике библиотеки времени выполнения.  
  
> [!NOTE]
>  Не используйте `str` семейство функций со строками Юникода, которые, скорее всего, содержат встроенные пустые байты. Аналогичным образом, не используйте `wcs` семейства функций с многобайтовой Кодировки (SBCS) строк.  
  
 В следующих примерах кода показано использование `_TCHAR` и `_tcsrev` сопоставление многобайтовой Кодировки, [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], моделям.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Если `_MBCS` был определен, препроцессор сопоставляет этот фрагмент следующему коду:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Если `_UNICODE` был определен, препроцессор сопоставляет этот фрагмент следующему коду:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Если ни одна из `_MBCS` , ни `_UNICODE` были определены, препроцессор сопоставляет этот фрагмент однобайтовому [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] кода, как показано ниже:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Таким образом можно написать код, обслуживать и компилировать единый исходный код файл для запуска с подпрограммами, использующими любую из трех описанных выше кодировок.  
  
## <a name="see-also"></a>См. также  
 [Текст и строки](../text/text-and-strings-in-visual-cpp.md)   
 [Использование типов данных TCHAR.H с кодом _MBCS](../text/using-tchar-h-data-types-with-mbcs-code.md)