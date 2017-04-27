---
title: "_inp, _inpw, _inpd | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _inp
- _inpw
- _inpd
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
dev_langs:
- C++
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: ec0c11cf43080389363fc682aad9511a958e6edd
ms.lasthandoff: 04/01/2017

---
# <a name="inp-inpw-inpd"></a>_inp, _inpw, _inpd
Вводит из порта байт (`_inp`), слово (`_inpw`) или двойное слово (`_inpd`).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `port`  
 Номер порта ввода-вывода.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эти функции возвращают байт, слово или двойное слово, прочитанное из порта `port`. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 Функции `_inp`, `_inpw`и `_inpd` считывают из указанного порта байт, слово и двойное слово соответственно. Входное значение может быть любым беззнаковым коротким целым числом в диапазоне от 0 до 65535.  
  
 Поскольку эти функции производят чтение непосредственно из портов ввода-вывода, они не могут использоваться в пользовательском коде в Windows NT, Windows 2000, Windows XP и Windows Server 2003.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_inp`|\<conio.h>|  
|`_inpw`|\<conio.h>|  
|`_inpd`|\<conio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)   
 [_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)
