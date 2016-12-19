---
title: "Оператор __if_not_exists | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_not_exists"
  - "__if_not_exists_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_not_exists - ключевое слово [C++]"
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор __if_not_exists
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор `__if_not_exists` проверяет, существует ли указанный идентификатор.  Если идентификатор не существует, выполняется определенный блок операторов.  
  
## Синтаксис  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`identifier`|Идентификатор, наличие которого требуется проверить.|  
|`statements`|Один или несколько операторов, которые будут выполнены, если `identifier` не существует.|  
  
## Заметки  
  
> [!CAUTION]
>  Для получения самых надежных результатов используйте оператор `__if_not_exists` при следующих ограничениях.  
  
-   Применяйте оператор `__if_not_exists` только к простым типам, а не шаблонам.  
  
-   Применяйте оператор `__if_not_exists` к идентификаторам как внутри, так и вне класса.  Не применяйте оператор `__if_not_exists` к локальным переменным.  
  
-   Используйте оператор `__if_not_exists` только в теле функции.  За пределами тела функции оператор `__if_not_exists` может проверять только полностью определенные типы.  
  
-   При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.  
  
 Дополнением к оператору `__if_not_exists` является оператор [\_\_if\_exists](../cpp/if-exists-statement.md).  
  
## Пример  
 Пример использования `__if_not_exists` см. в разделе [Оператор \_\_if\_exists](../cpp/if-exists-statement.md).  
  
## См. также  
 [Инструкции выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Оператор \_\_if\_exists](../cpp/if-exists-statement.md)