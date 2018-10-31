FROM debian
RUN apt-get update && apt-get install -y \
tcpdump
RUN mkdir /pcap
RUN cd /pcap
WORKDIR /pcap
EXPOSE 22
CMD tcpdump -w "$(date +'%Y-%m-%d_%H:%M:%S').pcap"