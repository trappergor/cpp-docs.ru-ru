---
title: "_amsg_exit | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _amsg_exit
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
apitype: DLLExport
f1_keywords:
- _amsg_exit
dev_langs:
- C++
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7ce90e59ba20f81b8737c5f53c99b7cbc0ff3fdf
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="amsgexit"></a>_amsg_exit
Создает указанное сообщение об ошибке времени выполнения, затем завершает приложение с кодом ошибки 255.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
```  
  
#### <a name="parameters"></a>Параметры  
 `rterrnum`  
 Идентификационный номер определяемого системой сообщения об ошибке времени выполнения.  
  
## <a name="remarks"></a>Примечания  
 Эта функция посылает сообщение об ошибке времени выполнения в поток **stderr** для консольных приложений или отображает сообщение в окне сообщения для приложений Windows. В режиме отладки перед выходом можно вызвать отладчик.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|_amsg_exit|internal.h|
