<a id="top"></a>

## Packages

### Reusable Module Example
See [@pdffiller/invite-teammates-modal/example](example/README.md)
### Reusable Module Interface
See [@pdffiller/invite-teammates-modal/interface](interface/README.md)

# Invite Teammates Modal
It is used to invite users to your organization via email or an invitation link.

[Design](link), [Confluence](https://pdffiller.atlassian.net/wiki/spaces/MAC/pages/4181950664/Invite+Teammates+Modal)

[Playground](https://reimagined-adventure-9kk1nrp.pages.github.io/?path=/story/reusable-modules-invite-teammates-modal--invite-teammates-modal)

Used:
- [/account/organization](https://reg.pdffillers.com/en/account/organization) (invite users)

## Contents
1. [Builds](#builds)
2. [Starting local development](#local_dev)
3. [Params](#params)
4. [Update version](#update_version)
5. [Storybook](#storybook)

<a id="builds"></a>
## Builds
| GitHub actions                                                                                                   | CP builds                                                                                                            |
|------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| [DEV](https://github.com/pdffiller/front-invite-teammates-modal/actions/workflows/reusable-deploy-to-dev.yaml)   | [DEV](https://reg.pdffillers.com/33UMW1ZQ6goFeZ2o/?op=frontend_builds&op1=appBuilds&app_name=InviteTeammatesModal_1) |
| [RC](https://github.com/pdffiller/front-invite-teammates-modal/actions/workflows/reusable-deploy-to-rc.yaml)     | [RC](https://cp.pdffiller-rc.xyz/33UMW1ZQ6goFeZ2o/?op=frontend_builds&op1=appBuilds&app_name=InviteTeammatesModal_1) |
| [PROD](https://github.com/pdffiller/front-invite-teammates-modal/actions/workflows/reusable-deploy-to-prod.yaml) | [PROD](https://cp.pdffiller.com/33UMW1ZQ6goFeZ2o/?op=frontend_builds&op1=appBuilds&app_name=InviteTeammatesModal_1)  |

```shell
yarn run build
```

<a id="local_dev"></a>
## Starting local development
Node.js = 18.x

[Local template](build/index.ejs) (where you can change the user ID)

```shell
yarn install
yarn start # Module development
yarn start:all # Module + interface + example development
```

Remember to set the `BACKEND=reg` parameter before starting the project, example:
`BACKEND=reg yarn start`

<a id="params"></a>
## Params
```typescript
export type Params = {
  onClose?: () => void,
  modalType?: string,
  hasSuccessModal?: boolean,
  hasContactSalesModal?: boolean,
  contactSalesModalProps?: {
    handleClose?: () => void,
    handleCancel?: () => void,
    handleSubmit?: () => void,
    handleError?: ()=> void,
    texts?: {
      title?: string,
      description?: string,
      btnConfirmText?: string,
      btnCancelText?: string,
    },
    submitData?: {
      [key: string]: unknown
    },
    icon?: React.Component,
    successModalProps?: {
      [key: string]: unknown
    }
    disableErrorModal: boolean
  }
  isAdbAvailable?: boolean,
  [key: string]: unknown,
};
```

<a id="update_version"></a>
## Update version
```shell
npm version minor  # [major.minor.patch]
```

<a id="storybook"></a>
## Storybook
```shell
yarn start:ui
```

[Top](#top)
