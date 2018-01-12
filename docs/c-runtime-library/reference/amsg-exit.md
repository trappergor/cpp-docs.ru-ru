---
title: "_amsg_exit | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _amsg_exit
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
f1_keywords: _amsg_exit
dev_langs: C++
helpviewer_keywords: _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42981b60a0a3f53c0887fad45bdd41d7ffd2c308
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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