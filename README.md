# AAVE Automation Subgraph

Tracks the data related to Submit, Execute and Cancel automation.

Subgraph deployment:

- Polygon: [https://thegraph.com/hosted-service/subgraph/richa-iitr/aave-automation-polygon?selected=playground](https://thegraph.com/hosted-service/subgraph/richa-iitr/aave-automation-polygon?selected=playground)
- Avalanche: [https://thegraph.com/hosted-service/subgraph/richa-iitr/aave-automation-avalanche?selected=playground](https://thegraph.com/hosted-service/subgraph/richa-iitr/aave-automation-avalanche?selected=playground)

Query Structure

<pre>
{
  accounts{
    id
    user
    submitAutomation{
      id
      user
      userId
      safeHF
      thresholdHF
      currentHf
      transactionDetail{
        id
        blockNumber
        timeStamp
        transactionHash
        transactionLogIndex
        logIndex
      }
    }
    executeAutomation{
      id
      user
      userId
      nonce
      finalHf
      initialHf
      automationFee
      isSafe
      metaData
      params{
        id
        collateralToken
        collateralAmount
        debtToken
        debtAmount
        collateralAmountWithTotalFee
        swap{
          id
          sellToken
          buyToken
          sellAmt
          unitAmt
          callData
        }
        route
        rateMode
      }
      transactionDetail{
        id
        blockNumber
        timeStamp
        transactionHash
        transactionLogIndex
        logIndex
      }
    }
    cancelData{
      id
      user
      userId
      nonce
      transactionDetail{
        id
        blockNumber
        timeStamp
        transactionHash
        transactionLogIndex
        logIndex
      }
    }
    systemCancelData{
      id
      user
      userId
      nonce
      errorCode
      transactionDetail{
        id
        blockNumber
        timeStamp
        transactionHash
        transactionLogIndex
        logIndex
      }
    }
  }
  feeTransferDatas{
    id
    recipient
    from
    tokens
    amount
    transactionDetail{
      id
      blockNumber
      timeStamp
      transactionHash
      transactionLogIndex
      logIndex
    }
  }
  updateMinHfDatas{
    id
    oldMinHf
    newMinHf
    transactionDetail{
      id
      blockNumber
      timeStamp
      transactionHash
      transactionLogIndex
      logIndex
    }
  }
  updateBufferHfDatas{
    id
    oldBuffer
    newBuffer
    transactionDetail{
      id
      blockNumber
      timeStamp
      transactionHash
      transactionLogIndex
      logIndex
    }
  }
  updateAutomationFeeDatas{
    id
    oldAutomationFee
    newAutomationFee
    transactionDetail{
      id
      blockNumber
      timeStamp
      transactionHash
      transactionLogIndex
      logIndex
    }
  }
  changedOwners{
    id
    oldOwner
    newOwner
    transactionDetail{
      id
      blockNumber
      timeStamp
      transactionHash
      transactionLogIndex
      logIndex
    }
  }
  systemCallDatas{
    id
    sender
    actionId
    metaData
    transactionDetail{
      id
      blockNumber
      timeStamp
      transactionHash
      transactionLogIndex
      logIndex
    }
  }
  executors{
   id
   executors
  }
}
</pre>
