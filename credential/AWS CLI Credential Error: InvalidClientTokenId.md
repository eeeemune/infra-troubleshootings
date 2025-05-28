# AWS CLI Credential Error: InvalidClientTokenId

# 😵 Error Situation
## Error Message
```shell
An error occurred (InvalidClientTokenId) when calling the GetCallerIdentity operation: The security token included in the request is invalid.
```
# 🤔 Why was it Happened?
## Reason
This error is typically happened when you **missed ****`aws_session_token`**
# 😋 Solution
## 1. Get Your Token ID

![](https://prod-files-secure.s3.us-west-2.amazonaws.com/e7a75158-b9c4-4d57-84fa-9858bfaefc38/717049e6-e05a-4ccd-a847-1bd21b2a20ca/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB46665GXFUQR%2F20250528%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20250528T162047Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEK%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJHMEUCIF62%2BBy7MkKgkujru7Jdi8kqoi4v90Gp25wtHLygwTcQAiEAuXujJyJqnwxEdoZjsLTpfjfGWnvm%2BzpP9kGbstFNtdkq%2FwMIeBAAGgw2Mzc0MjMxODM4MDUiDNspZU9IH54tWn0D%2BircAz7HMnSf%2FNFqGnLkCBPKh7lKFtveiCDCwyyoIabdrJxf5XI%2FBr%2FYlUpdsx2aD0KHhj1Sesq8gpNnbPchbS57iTmJ2mSx%2FWh9WwRvOtsi30h%2BTINLi2d8jX92LmdxJ7nCnlp18OCgKJ%2FuCk%2BVtQ0XQ32SDWC2f7nNSp08faFzvJY4YHwFkFFQq3LfLnCX%2FYDdBJSuDBJq9OATnOiyuugtSvJ2cy9uLIfAR6kkaDt8sapzLPwY%2B6YpBfqj4iWd88C1J4xLYD0NiQxxNVHiRWHUIdKRy1SZYTzbnS0gHx%2BY0OgNqy7z6n62Cyt4ifaFW6e5xdp21RqGf%2Be83BIbMtjl4usnHcwCsmgxwIVHGtkeMx6XpeFuhpALnxzLtqW8ardSIsof%2FPm5MnbG7OyfZ4TKpzJkkTLPoyw6ciNcT6JzCYV4%2Fk1M%2BO15AAAgwJ%2F373yGVHNwztrxk%2BYi%2FqrjnI32nDZioUEfyx5qvn0z7GK39OZJFJ6Ek0lpMCUkQMhVTh2CrSQnen3VIWYL4%2BQIS4De4UHEspIAAHgFA4h0nC3swkuzKFQ4OOZ%2BHnbrnSmoUfOxSFnS8gCqjvsN5bGIxU4aUj1CEmIEcTp3WvGjOhmz32%2FILuYjB08vpQ%2F26EtUMI7G3MEGOqUBek89eUwCOkxw8mu53WqGYNoYnS6H7ykkUTKaI4NUK0EgZrg68xNOX3lGkSa76j2ktZHs5EIGWzLsZ30MNAqeO1PI2NveGbSJHnI%2B%2FC33TcNxjkwzZEP3y2BE4dRXWbqZCQg3kBp%2FxY16FfbrGsRlDuAiu5zqmzi%2FqRPWuoYSQnGsqgymYHmrFfck4Dzyp2kcEaB%2BH%2FAhHK%2Fiy%2BFm87fQN5oQmcr7&X-Amz-Signature=57cbb4938a53f9c683d9677d6e968e7af26b03a9e9e5a8801b5a19839531103f&X-Amz-SignedHeaders=host&x-id=GetObject)

## 2. Register Token ID to Credential File
### Turn on aws credential file
```typescript
vim ~/.aws/credentials
```
### Paste Token to The File
```typescript
aws_access_key_id = ASIAxxxxxxxxxxxxxxxx
aws_secret_access_key = your-secret-key
aws_session_token = your-session-token-here
```
## 3. Test The Connection
```typescript
aws sts get-caller-identity
```
