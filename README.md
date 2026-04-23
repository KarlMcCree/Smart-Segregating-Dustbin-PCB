# Smart-Dustbin
Most online “smart dustbins” only offer automatic lid opening and basic fill level detection. This project goes far beyond by adding intelligent waste segregation, real-time cloud monitoring, voice feedback, and odor control – all in a compact, battery‑operable, real‑world enclosure.

How it works (step‑by‑step flow):

User approaches – Ultrasonic sensor detects hand / object within 20 cm.

Lid opens – High‑torque servo rotates lid (≈ 90°).

Fan starts – Odor control fan runs for 10 seconds.

Waste is dropped – Waste falls onto a small inclined chute.

Metal detection – Inductive sensor at the chute exit checks for metal.

Metal detected → ESP32 moves flap servo to guide waste into Metal Bin.

No metal → flap stays in default position, waste goes into General Bin.

Voice feedback – DFPlayer plays “Metal” or “Non‑metal” accordingly.

Lid closes – After 3 seconds of no further motion.

Fill level update – Two time‑of‑flight (or ultrasonic) sensors measure remaining space in each bin.

OLED update – Display shows % full for both bins + last detection.

Cloud upload – Every 30 seconds, ESP32 sends bin fullness and metal count to Blynk / MQTT.
