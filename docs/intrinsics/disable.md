---
title: "_disable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_disable_cpp"
  - "_disable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_disable intrinsic"
  - "disable intrinsic"
  - "rsm instruction"
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _disable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Отключение прерываний.  
  
## Синтаксис  
  
```  
void _disable(void);  
```  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_disable`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 `_disable` Указывает процессору очистить флаг прерывания.  На платформе x86 систем, эта функция создает инструкцию снятия флага прерывания \(`cli`\) .  
  
 Эта функция доступна только в режиме ядра.  При использовании в пользовательском режиме, исключение привилегированной инструкции во время выполнения отбрасывается.  
  
 На платформах ARM эта процедура доступна только как встроенная.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)