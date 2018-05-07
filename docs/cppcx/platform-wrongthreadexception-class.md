---
title: Класс Platform::WrongThreadException | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
dev_langs:
- C++
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f01b52470f5c70c588c7905a2c46f7cae9b26d06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformwrongthreadexception-class"></a>Класс Platform::WrongThreadException
Вызывается, если поток выполняет вызов посредством указателя на интерфейс для прокси-объекта, который не принадлежит подразделению потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## <a name="see-also"></a>См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)