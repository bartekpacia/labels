# labels

This repository exist only to make cloning labels easy.

Inspired by the `flutter/flutter` repository and two open-source repositories I
had maintained for a longer time – `mobile-dev-inc/maestro` and
`leancodepl/patrol`.

## Usage

To copy labels from this repo into your repo:

```console
gh label clone bartekpacia/labels
```

To delete all labels:

```console
gh label list --json name | jq -r '.[] .name' | xargs -I {} gh label delete --yes {}
```

List all labels in the Flutter repo (which is an inspiration):

```console
gh label list --repo flutter/flutter --limit 500 --sort name
```

## Label philosophy

Only core labels, that I find generally useful in any project, are included in
this repository. You will likely want to add more project-specific labels.

### Platform-specific labels

<details>
<summary>create</summary>

```console
gh label create 'platform: android' -c 30B805 -d 'Testing Android apps is affected'
gh label create 'platform: ios' -c 295D99 -d 'Testing iOS apps is affected'
gh label create 'platform: web' -c 91529 -d 'Testing web apps is affected'
```

</details>

### Use prefixes to group labels

- `p` for `package`, e.g. `package: camera`, `package: video_player`
- `a` for `area`, e.g. `a: accessibility`, `a: layout`, `a: tests`
- `t` for `tool`, e.g. `t: gradle`, `t: xcode`
- `customer` for customer-specific labels, e.g. `customer: toyota`, `customer:
fuchsia`. For non-public customer names, codenames can be made-up, e.g.
`customer: cars` to not say "Toyota" out loud.

### Use colors to convey meaning

- For `platform: android` label, set the color to green – because green is
  associated with Android
- For priority labels, set the color to red – because red is associated with
  danger. The lower the priority, the less intense red is.
- Keep label colors consistent across repositories you maintain/work on
  regularly.
