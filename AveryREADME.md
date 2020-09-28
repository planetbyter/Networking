# Networking
For Networking Course 652
Avery Alexander Rijos
arijos0222@gmail.com

# Google's Jupiter vs Facebook's Data Center Fabric



To start, we will be examining Google's networking architecture, fueled by the dynamic "Clos Topology."" Large cluster networks such as Clos aids in deploying at a massive scale. At Google, the company haad many affiliated applications that benefitted greatly from this very high-bandwidth communication. This particular topology, with many benefits, does also introduce substantial challenges as well, including the managing of the fiber fanout and more complex routing across multiple "equal cost" paths. The pathway of data flows from the datacenter to the Wide Area Network (WAN). As time ensued, CPU intensive traffic engineering led to move control protocols onto external servers with more powerful CPU's.

  - Line cards provides interfaces to the network
  - Desired--at most-- a 2:1 oversubscription
  - Deployed in a Centauri Chassis

The centauri switch (a ToR switch) contained with each four chips serving a subnet of machines. Switches were then configured with a particular intended topology. Switches in this case learn actual network congifuration and link state through pair-wise neighbor discovery. Routing proceeds with each switch exchanging its own "view" of its local area of connectivity with a centralized Firepath master, which redistributes the "global link state" to all switches. The "neighbor discovery protocol" (NDP) then utilizes the newly configured view of cluster topology together with a switch's local id to determine the expected peer ID's of its local ports. The system then ultimately verifies the aforementioned via message exchange.

# Facebook's Data Center Fabric and the Limits of Clusters
Facebook as a company and organization had-- early in their career-- made its particular goal to understand the limits of "clusters" and how to best scale a data center in a more efficient, and topologically beauteous fashion. Firstly, the limits of clusters; a cluster is a unit of deployment involving many hundreds of "Top of the Rack (ToR)" switches, aggregated on large high radix cluster switches. The size of a clister, then, is ultimately limited by the port density of the cluster switch itself. The topology of clustering had predetermined the engineering of the infrastructure itself. Facebook with its Data Center Fabric (DCF) reserves, in comparison, an equal amount of uplink capacity on what they call "Pods" for each downlink: a 1:1 oversubscription ratio! The company realized that the ned for a high amount of ports is against the desire to provide the highest bandwidth infrastructure possible. In allocating more ports to accomodate inter-cluster traffic, we take away the density from the size of the cluster as a whole. This fabric was enginered using a 16 plane architecture, with 1.6T of capacity per rack. Server pods created high performance connectivity between individual server pods. A "Pod" in this sense is referenced as a "unit of network" (Andreyev). Each pod is connected ot at least 4 fabric switches. This creates a scalable architecture; more compute capacity? Add more server pods. More extra-fabric connectivity? Add edge pods or scale uplinks in the existing switches. This is what is known as the "top down" approach, where there exists only the minimum neecessary protocol features. Facebook also developed a centralized controller that is able to override routing paths by purely making software-level actions. From the Facebook building, to its campus, to its distributed networks: there is a great beauty in this architectural elegance and intuitive simplicity. 

- The network is all layer3-- from the ToR uplinks to the edges. Dual stacked, the network supports IPv4 and IPv6 technologies which provides the unique IP addresses necessary for Internet-enabled devices to communicate.

# Sources

[GitHub](http://github.com)
|
[Blog](https://polymathictendencies.blogspot.com/2020/06/polymathic-tendencies-blog-for-all.html)



