# Linksys Velop Pro 7 (LN6001/MBE70) Lab

Community OpenWrt firmware for the **Linksys Velop WRT Pro 7 (LN6001 / MBE70WRT)**.

## 日本語

Linksys Velop WRT Pro 7（LN6001 / MBE70WRT）向けのOpenWrtファームウェアです。

### リリース 260927

| 項目 | 内容 |
| --- | --- |
| リリース日 | 2026-09-27 |
| リリースブランチ | `260927` |
| バージョン | `25.12.26092713` |
| 製品 | Linksys Velop Pro 7 |
| 対応モデル | LN6001 / MBE70WRT |
| OpenWrt | `SNAPSHOT r0-e248cebd1a` |
| LuCI | `0.260709.71895` |
| LuCI base | `0.260927.22557` |
| Linux カーネル | `6.18.52` |

LuCI による管理画面と Auto-IPoE を含むコミュニティ向けリリースです。

### ダウンロードと確認状況

[firmware フォルダー](firmware/) から本リリースをダウンロードしてください。


### インストール

1. ルーターが **LN6001 / MBE70WRT** であり、もう一方のスロットに起動可能な純正
   ファームウェアが残っていることを確認します。
2. 必要な設定をバックアップし、PC を Ethernet で接続します。
3. Linksys 純正 Web インターフェースの手動ファームウェア更新画面を開きます。
4. 本リリースのダウンロードファイルを選択し、**設定を保持する**オプションを
   無効にします。
5. 更新を開始し、再起動が完了するまで電源を切らずに待ちます。
6. PC の DHCP リースを更新し、[http://192.168.1.1/](http://192.168.1.1/) を開きます。
7. CPE 底面ラベルに記載されたパスフレーズを使って root としてログインし、
   root パスワードを変更します。
8. **ネットワーク → 無線**で国コード、チャンネル、帯域幅、送信出力を確認します。

Wi-Fi のパスフレーズも CPE 底面のラベルに記載されています。

###  バックアップパーティションに切り替える方法

LN6001 は、起動を 3 回中断すると通常は別のファームウェアスロットを選択します。

1. 電源スイッチをONにして起動中に約 5 秒後に電源スイッチを切ります。
2. この操作を合計 3 回行います。
3. 4 回目は電源を入れたまま数分待つと、バックアップスロットが起動します。

### 補足

- このリリースは **LN6001 / MBE70WRT 専用**です。
- LuCiのファームウェア更新メニューよりインストール可能です。raw `mtd`
  書き込みや強制 `sysupgrade` は対象外です。

[LICENSES.md](LICENSES.md) に記載された各コンポーネントのライセンスに基づき、
現状有姿で提供されます。

---

## English

### Release 260927

| Item | Value |
| --- | --- |
| Release date | 2026-09-27 |
| Release branch | `260927` |
| Version | `25.12.26092713` |
| Product | Linksys Velop Pro 7 |
| Supported models | LN6001 / MBE70WRT |
| OpenWrt | `SNAPSHOT r0-e248cebd1a` |
| LuCI | `0.260709.71895` |
| LuCI base | `0.260927.22557` |
| Linux kernel | `6.18.52` |

This community release includes the LuCI administration interface and Auto-IPoE.

### Download and verification status

Download this release from the [firmware directory](firmware/).

### Installation

1. Confirm that the router is an **LN6001 / MBE70WRT** and that the other slot
   still contains bootable stock firmware.
2. Back up any settings you need and connect the computer by Ethernet.
3. Open the manual firmware-update page in the Linksys stock web interface.
4. Select the downloaded release file and disable **Keep settings**.
5. Start the update and keep the router powered on until it finishes rebooting.
6. Renew the computer's DHCP lease and open
   [http://192.168.1.1/](http://192.168.1.1/).
7. Sign in as root using the passphrase printed on the CPE's bottom label, then
   change the root password.
8. Review the country code, channel, channel width, and transmit power under
   **Network → Wireless**.

The Wi-Fi passphrase is also printed on the CPE's bottom label.

### Switching to the backup partition

The LN6001 normally selects the other firmware slot after three interrupted
boot attempts.

1. Turn the power switch on, then turn it off after about five seconds while
   the router is starting up.
2. Repeat this sequence three times in total.
3. On the fourth power-on, leave the router powered on for several minutes
   until it boots from the backup slot.

### Notes

- This release is for the **LN6001 / MBE70WRT only**.
- You can install this release through the firmware update menu in LuCI.
  Raw `mtd` writes and forced `sysupgrade` are outside this procedure.

See [LICENSES.md](LICENSES.md). The firmware is provided as-is under the
licenses of its included components.
