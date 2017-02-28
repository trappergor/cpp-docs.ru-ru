---
title: "_outp, _outpw, _outpd | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
dev_langs:
- C++
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0bece17df9233570753cd318d28a88254eaaf74f
ms.lasthandoff: 02/24/2017

---
# <a name="outp-outpw-outpd"></a>_outp, _outpw, _outpd
Выводит на порт байт (`_outp`), слово (`_outpw`) или двойное слово (`_outpd`).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _outp(  
unsigned short port,  
int databyte   
);  
unsigned short _outpw(  
unsigned short port,  
unsigned short dataword   
);  
unsigned long _outpd(  
unsigned short port,  
unsigned long dataword   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *порт*  
 Номер порта.  
  
 *databyte, dataword*  
 Выходные значения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции возвращают выходные данные. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 Функции `_outp`, `_outpw`и `_outpd` пишут байт, слово и двойное слово, соответственно, на указанный порт вывода. Аргумент *порт* может быть любым целым числом без знака в диапазоне от 0 до 65535; *databyte* может быть любым целым числом в диапазоне от 0 до 255; *dataword* может быть любым значением в диапазоне целого числа, короткого целого без знака и длинного целого без знака, соответственно.  
  
 Поскольку эти функции пишут непосредственно на порт ввода-вывода, они не могут использоваться в пользовательском коде в Windows NT, Windows 2000, Windows XP и Windows Server 2003. Для получения дополнительных сведений об использовании портов ввода-вывода в этих операционных системах, выполните поиск по запросу "Последовательная связь в Win32" в MSDN.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_outp`|\<conio.h>|  
|`_outpw`|\<conio.h>|  
|`_outpd`|\<conio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)   
 [_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
