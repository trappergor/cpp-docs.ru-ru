---
title: Метод FtmBase::UnmarshalInterface | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a1991454daa76fcf7878a7487080124b5a34dbeb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644038"
---
# <a name="ftmbaseunmarshalinterface-method"></a>Метод FtmBase::UnmarshalInterface
Инициализирует только что созданный прокси-сервер и возвращает указатель интерфейса для этого прокси-сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
### <a name="parameters"></a>Параметры  
 *pStm*  
 Указатель на поток, из которого должен быть неупакованный указатель на интерфейс.  
  
 *riid*  
 Ссылка на идентификатор интерфейса необходимо распаковать.  
  
 *ppv*  
 После завершения операции адрес переменной указателя, получающей указатель интерфейса, запрашиваемый в *riid*. Если операция выполнена успешно, **ppv* содержит запрошенный указатель интерфейса интерфейса необходимо распаковать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае — значение E_NOINTERFACE или E_FAIL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)